.. _orocloud-maintenance-advanced-use:

Advanced Configuration
======================

.. contents:: :local:
   :depth: 1

Deployment and Maintenance Configuration
----------------------------------------

To modify configuration options for maintenance agent, you need to have the `orocloud.yaml` file placed in the application root. If the application is not yet deployed, modifications can also be made in `/mnt/(ocom|ocrm)/app/orocloud.yaml`.

.. note:: Please do not use double quotes for any variables. Use single quotes instead.

.. note:: Please do not use tabs in `orocloud.yaml` as indentations as they are treated differently by different editors and tools. Since indentation is crucial for  proper interpretation of YAML, **use spaces only**.

With `orocloud.yaml` it is possible to override the following nodes:

**install_commands**

.. code-block:: none
    :linenos:

    ---
    orocloud_options:
      deployment:
        install_commands: # Application commands which run during the installation process
          - 'oro:install --sample-data=n --user-name=admin --user-email=admin@example.com --user-password=new_password --user-firstname=John --user-lastname=Doe --application-url=https://example.com --organization-name=Oro'

.. note:: As most of time the `deploy` operation runs only once, it is recommended to avoid storing any sensitive data (such as email, username, or password) in any files for security purposes. You can omit options like `user-name`, `user-email` or `user-password`. When omitted, they are asked interactively during the `deploy` operation.

**upgrade_commands**

.. code-block:: none
    :linenos:

    ---
    orocloud_options:
      deployment:
        upgrade_commands: # Application commands which run during update process
          - 'oro:platform:update'

**composer_command**

.. code-block:: none
    :linenos:

    ---
    orocloud_options:
      deployment:
        composer_command: '{{composer_cmd}} install --no-dev --optimize-autoloader'

.. note:: Please note that ``{{composer_cmd}}`` is a reserved variable and in most cases during executions it will be replaced with the ``composer`` value. Please, keep in mind that the command format is IMPORTANT and should take the following form: ``{environment variables} {{composer_cmd}} {command} {option1 option2 ... option n}``.

For example:

* '{{composer_cmd}} install --no-dev -vvv'
* 'COMPOSER=dev.json {{composer_cmd}} install --no-dev -vvv'

Some options may also be omitted as they are added automatically:

* The `--working-dir (-d)` option will be ignored because it is added automatically during the `deploy` | `upgrade` command.
* The `--no-interaction (-n)` option will be ignored because it is added automatically during the `deploy` | `upgrade` command.
* The `-v|vv|vvv, --verbose` option will be used (if specified) with a higher priority than the same option in the `deploy` | `upgrade` command, e.g. ``orocloud-cli deploy -vv``.

**after_composer_install_commands**

.. code-block:: none
    :linenos:

    ---
    orocloud_options:
      deployment:
        after_composer_install_commands:
          - 'command1'

**db_extensions**

.. code-block:: none
    :linenos:

    ---
    orocloud_options:
      deployment:
        db_extensions:
          - 'uuid-ossp'
          - 'pgcrypto'

**before_backup_create_commands**

.. code-block:: none
    :linenos:

    ---
    orocloud_options:
      deployment:
        before_backup_create_commands:
          - 'command1'
          - 'command2'

**after_backup_create_commands**

.. code-block:: none
    :linenos:

    ---
    orocloud_options:
      deployment:
        after_backup_create_commands:
          - 'command1'
          - 'command2'


Application Configuration
-------------------------

Custom maintenance page, web backend prefix, and consumers debug mode can be configured the following way:

.. code-block:: none
    :linenos:

    ---
    orocloud_options:
      application:
        maintenance_page: '/mnt/ocom/app/www/maintenance.html'
        web_backend_prefix: '/my_admin_console_prefix'
        consumers_debug_mode: true

.. note:: ``/mnt/ocom/app/www`` is the application root path for the `OroCommerce` application type. For `OroCRM`, use the ``/mnt/ocrm/app/www`` path. The `maintenance.html` file should be available in application repository in the specified path. When modified, changes are applied after the `deploy` | `upgrade` operation in approximately 30 minutes.

Webserver Configuration
-----------------------

Webserver configuration can be modified, as illustrated below:

.. code-block:: none
    :linenos:

    ---
    orocloud_options:
      webserver:
        redirects_map:
          '/about_us_old': '/about'
          '/about_them_old': '/about_them'
        locations:
          'root':
            type: 'php'
            location: '~ /app\.php(/|$)'
            auth_basic_enable: true
            auth_basic_userlist:
              user1:
                ensure: 'present'
                password: 'password1'
              user2:
                ensure: 'absent'
                password: 'password2'
          'admin':
            type: 'php'
            location: '~ /app\.php(/admin|$)'
            auth_basic_enable: true
            auth_basic_userlist:
              user3:
                ensure: 'present'
                password: 'password1'
              user4:
                ensure: 'absent'
                password: 'password2'
            allow:
              - '127.0.0.1'
              - '127.0.0.2'
            deny:
              - 'all'
          'de':
            type: 'php'
            location: '/de'
            fastcgi_param:
              'WEBSITE': '$host/de'
            allow:
              - '127.0.0.1'
              - '127.0.0.2'
            deny:
              - 'all'
          'en':
            type: 'php'
            location: '/en'
            fastcgi_param:
              'WEBSITE': '$host/en'
            allow:
              - '127.0.0.1'
              - '127.0.0.2'
            deny:
              - 'all'
        access_policy:
          'ip':
            'type'  : 'allow'
            'allow' :
              - '127.0.0.1'
              - '192.168.0.1'
              - '172.16.0.0/16'
            'deny'  :
              - '10.0.0.1'
          'country':
            'type'  : 'deny'
            'allow' :
              - 'US'
              - 'CA'
          'ua':
            'allow' :
              - 'GoogleStackdriverMonitoring'
              - 'Some Custom agent'
            'deny'  :
              - 'AcoiRobot'
              - 'Wget'
          'uri':
            'allow' :
              - '~(^/api/(.*))'
        limit_whitelist:
          - '8.8.8.8'
          - '10.1.0.0/22'
        limit_whitelist_uri:
          - '~(^/admin/test/(.*))'
        blackfire_options:
          agent_enabled : true
          server_id     : '<server-id>'
          server_token  : '<server-token>'
          log_level     : '1'
          log_path      : '/var/log/blackfire/agent.log'

* **redirects_map** — the hash where the key is an old URL and the value is a new URL
* **locations** — the hash of hashes. The top key is location name, the lower keys are:

   * `type` — location type. Possible values are 'php', 'static', 'rewrite'.
   * `location` — location URI. The value may have regular expressions and modifiers as it is used in the NginX location directive.
   * `fastcgi_param` — the hash for php-specific custom variables.
   * `auth_basic_enable` — a boolean trigger for HTTP basic authentication.
   * `auth_basic_userlist` — the hash of hashes with user name as a key and mandatory nested keys:
   
      * `ensure` — ensure if user is **present** or **absent**.
      * `password` — a plain text user password.
      
   * `allow` — an array of IP addresses or network masks allowed to access location. Use one record per line or 'any' to allow access from anywhere.
   * `deny` — an array of IP addresses or network masks denied to access location. Use one record per line or 'any' to deny access from anywhere.
* **access_policy** — the hash of hashes used to configure Web Application Firewall. The policy type may by default be set to 'allow' or 'deny', except for the user agent policy which may only be 'allow'.

   * `ip` — configure access limitations for a single IP address or network.
   * `country` — allow or deny access from some countries using GeoIP database.
   * `ua` — allow or deny access for specific user agents.
   * `uri` — set access permissions for a specific URI.
* **limit_whitelist** — configure IP address/range whitelist for NginX limit_req module.
* **limit_whitelist_uri** — configure URI whitelist for NginX limit_req module.
* **blackfire_options** — the hash used to configure Blackfire agent on environment

   * `agent_enabled` — boolean trigger for Blackfire installation
   * `server_id` — server ID string. Refer your Blackfire account to this value.
   * `server_token` — server token string. Refer your Blackfire account to this value.
   * `log_level` — Blackfire agent log verbosity.
   * `log_paht` — path to the log file location.

.. _orocloud-maintenance-advanced-use-sanitization-conf:

Sanitizing Configuration
------------------------

Regardless of application type (OroCommerce or OroCRM), each has its own default sanitize rules (`sanitize.method.rawsql` and `sanitize.method.update`). However, you can add your own rules, remove a specific default rule, or completely override them.

The sanitize configuration is grouped under the `sanitize` node and supports the following sanitize methods:

* **sanitize.rawsql_add_rules** — the list of raw SQL queries that helps you to sanitize the existing data, for example, delete data using the TRUNCATE method, UPDATE data to apply any custom modification, etc.

* **sanitize.rawsql_delete_rules** —  the list of raw SQL queries, which should be removed from the list in `sanitize.method.rawsql`. The format is the same as `sanitize.rawsql_add`.

* **sanitize.rawsql_override_rules** —  the list of raw SQL queries, which will be applied to sanitizing data and override default sanitize rule `sanitize.method.rawsql`. Please note, that if this option is specified, all `sanitize.rawsql_add_rules` and `sanitize.rawsql_delete_rules` will be ignored. The format is the same as `sanitize.rawsql_add_rules`.

* **sanitize.update_add_rules** — the mapping between specific table columns and the sanitizing method that should be used for the values.

* **sanitize.update_delete_rules** — the list of rules which will be deleted from the list in `sanitize.method.update`. The format is the same as in `sanitize.update_add_rules`.

* **sanitize.update_override_rules** — the list of rules which will be applied to sanitizing data and overriding the default sanitize rule `sanitize.method.update`. Please note, that if this option is specified, all `sanitize.update_add_rules` and `sanitize.update_delete_rules` will be ignored. The format is the same as `sanitize.update_add_rules`.

.. note:: Please keep in mind that **ALL** values in `rawsql_*_rules` and `update_*_rules` **MUST** be wrapped in **SINGLE** quotes.

.. code-block:: none
      :linenos:

      ---
      orocloud_options:
        deployment:
          sanitize:
            rawsql_add_rules:
              - 'TRUNCATE oro_message_queue_job_unique_test'
            rawsql_delete_rules:
              - 'TRUNCATE oro_tracking_visit_event'
              - 'TRUNCATE oro_tracking_website CASCADE'
            rawsql_override_rules:
              - 'TRUNCATE oro_tracking_visit_event'
              - 'TRUNCATE oro_tracking_website CASCADE'
            update_add_rules:
              - '{ table: oro_email_test, columns: [{name: subject, method: md5}, {name: from_name, method: md5}] }'
            update_delete_rules:
              - '{ table: oro_integration_transport, columns: [{name: api_key, method: md5},{name: api_user, method: md5},{name: api_token, method: md5}] }'
            update_override_rules:
              - '{ table: oro_integration_transport, columns: [{name: api_key, method: md5},{name: api_user, method: md5},{name: api_token, method: md5}] }'
            custom_email_domain: 'example.com'

General Conventions
^^^^^^^^^^^^^^^^^^^

Please use the following conventions to design your `sanitize.update_*` strategy:

* Provide sanitizing configuration for every table as a new item:

  .. code-block:: none
      :linenos:

      update_add_rules:
            - '{ table: oro_address, columns: [{name: street, method: md5}, {name: city, method: md5}, {name: postal_code, method: md5}, {name: last_name, method: md5}] }'
            - '{ table: oro_business_unit, columns: [{name: email, method: email}, {name: name, method: md5}, {name: phone, method: md5}] }'

* Provide the table name in the table node.
* In the columns section, provide an array of column name and sanitizing method pairs for all the columns that should be sanitized in the mentioned table.

  For example:

  .. code-block:: none
      :linenos:

      columns: [{name: street, method: md5}, {name: city, method: md5} ]

* Provide the column name in the name node. Use the following sanitize methods/strategies (ensure they reasonably match the column type):

  * `md5` — Replaces the original string with the string hash.
  * `email` — Replaces the email with the sanitized version of the email. When the `sanitize.custom_email_domain` configuration parameter is provided in the `deployment.yml` or `orocloud.yaml` files, the email strategy replaces the real email domain with the custom one provided as `sanitize.custom_email_domain`. If the custom domain is not provided, the sanitized email will be generated randomly. For example, `example@example.com`.
  * `date` — Replaces the date values with the current date and time.
  * `attachment` — Replaces the attachment file content with a dummy blank image.

Elasticsearch Synonyms Configuration
------------------------------------

To configure synonyms in Elasticsearch service, use the following field in orocloud.yaml:

.. code-block:: none
   :linenos:

    orocloud_options:
      elasticsearch:
        synonyms:
          'index_name1':
            - 'foo, bar, baz'
            - 'spam, eggs, meal'
            - 'null, void'
          'index_name2':
            - 'Alice, Bob, Dave, John'

You can use separate synonym lists for each index, or use '*' as index name in order to apply the same synonyms list to all indices.

.. code-block:: none
   :linenos:

    orocloud_options:
      elasticsearch:
        synonyms:
          '*':
            - 'foo, bar, baz'
            - 'spam, eggs, meal'
            - 'null, void'
            - 'Alice, Bob, Dave, John'

.. note:: Please keep in mind that synonyms configuration will be not applied immediately. All changes made in orocloud.yaml require up to 40 minutes to apply. More details for synonyms usage may be found in `official Elasticsearch documentation <https://www.elastic.co/guide/en/elasticsearch/reference/current/analysis-synonym-tokenfilter.html>`__.
