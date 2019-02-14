Configuration
=============

Postgresql Configuration
------------------------

Postgresql Database settings can be set using a `~/.config/ocdskingfisher-process/config.ini` file. A sample one is included in the
main directory.


.. code-block:: ini

    [DBHOST]
    HOSTNAME = localhost
    PORT = 5432
    USERNAME = ocdsdata
    PASSWORD = FIXME
    DBNAME = ocdsdata


It will also attempt to load the password from a `~/.pgpass` file, if one is present.

You can also set the `KINGFISHER_PROCESS_DB_URI` environmental variable to use a custom PostgreSQL server, for example
`postgresql://user:password@localhost:5432/dbname`.

The order of precedence is (from least-important to most-important):

  -  config file
  -  password from `~/.pgpass`
  -  environmental variable

Web Configuration
-----------------

TODO write up the API Key - notes: KINGFISHER_PROCESS_WEB_API_KEYS env var or [WEB] API_KEYS= in ini. Comma seperated.

Collection Defaults Configuration
---------------------------------

When you create a new collection, certain flags are set on it automatically. You can configure what the default values for them are:

.. code-block:: ini

    [COLLECTION_DEFAULT]
    CHECK_DATA = true
    CHECK_OLDER_DATA_WITH_SCHEMA_1_1 = false


Logging Configuration
---------------------

This tool will provide additional logging information using the standard Python logging module, with loggers in the "ocdskingfisher"
namespace.

When using the command line tool, it can be configured by setting a `~/.config/ocdskingfisher-process/logging.json` file.
A sample one is included in the main directory.


Redis Configuration
-------------------

You need an Redis server if you want a background que to process items immedietly. If you aren't using the background que, you don't need a Redis server.


.. code-block:: ini

    [REDIS]
    HOST = localhost
    PORT = 6379
    DATABASE = 0
