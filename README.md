# Servidor Alpine LAP com Extensões

Forneced uma pilha básica usando Alpine Linux, Apache2 e PHP 7.3, carregando algumas extensões.

## O que está incluído nessa imagem

bash, apache2, php7.3, php7.3-apache2, curl, ca-certificates, git php7.3-phar, php7.3-mcrypt, php7.3-soap, php7.3-openssl, php7.3-gmp, php7.3-pdo_odbc, php7.3-json, php7.3-dom, php7.3-pdo, php7.3-zip, php7.3-mysqli, php7.3-sqlite3, php7.3-pdo_pgsql, php7.3-bcmath, php7.3-gd, php7.3-odbc, php7.3-pdo_mysql, php7.3-pdo_sqlite, php7.3-gettext, php7.3-xmlreader, php7.3-xmlrpc, php7.3-bz2, php7.3-iconv, php7.3-pdo_dblib, php7.3-curl, php7.3-ctype, php7.3-session, php7.3-redis.


## Variáveis de ambiente

Algumas variáveis env podem ser definidas em tempo de execução pelo comando docker ou do docker-compose.

| Variável 	                    | Descrição 	|
|----------	                    |-----------	|
| APACHE_SERVER_NAME            | Muda o nome do servidor para combinar com o nome de domínio definido no arquivo httpd.conf |
| PHP_SHORT_OPEN_TAG            | Altera o php.ini 'short_open_tag' |
| PHP_OUTPUT_BUFFERING          | Altera o php.ini 'output_buffering' |
| PHP_OPEN_BASEDIR              | Altera o php.ini 'open_basedir' |
| PHP_MAX_EXECUTION_TIME        | Altera o php.ini 'max_execution_time' |
| PHP_MAX_INPUT_TIME            | Altera o php.ini 'max_input_time' |
| PHP_MAX_INPUT_VARS            | Altera o php.ini 'max_input_vars' |
| PHP_MEMORY_LIMIT              | Altera o php.ini 'memory_limit' |
| PHP_ERROR_REPORTING           | Altera o php.ini 'error_reporting' |
| PHP_DISPLAY_ERRORS            | Altera o php.ini 'display_errors' |
| PHP_DISPLAY_STARTUP_ERRORS    | Altera o php.ini 'display_startup_errors' |
| PHP_LOG_ERRORS                | Altera o php.ini 'log_errors' |
| PHP_LOG_ERRORS_MAX_LEN        | Altera o php.ini 'log_errors_max_len' |
| PHP_IGNORE_REPEATED_ERRORS    | Altera o php.ini 'ignore_repeated_errors' |
| PHP_REPORT_MEMLEAKS           | Altera o php.ini 'report_memleaks' |
| PHP_HTML_ERRORS               | Altera o php.ini 'html_errors' |
| PHP_ERROR_LOG                 | Altera o php.ini 'error_log' |
| PHP_POST_MAX_SIZE             | Altera o php.ini 'post_max_size' |
| PHP_DEFAULT_MIMETYPE          | Altera o php.ini 'default_mimetype' |
| PHP_DEFAULT_CHARSET           | Altera o php.ini 'default_charset' |
| PHP_FILE_UPLOADS              | Altera o php.ini 'file_uploads' |
| PHP_UPLOAD_TMP_DIR            | Altera o php.ini 'upload_tmp_dir' |
| PHP_UPLOAD_MAX_FILESIZE       | Altera o php.ini 'upload_max_filesize' |
| PHP_MAX_FILE_UPLOADS          | Altera o php.ini 'max_file_uploads' |
| PHP_ALLOW_URL_FOPEN           | Altera o php.ini 'allow_url_fopen' |
| PHP_ALLOW_URL_INCLUDE         | Altera o php.ini 'allow_url_include' |
| PHP_DEFAULT_SOCKET_TIMEOUT    | Altera o php.ini 'default_socket_timeout' |
| PHP_DATE_TIMEZONE             | Altera o php.ini 'date.timezone' |
| PHP_PDO_MYSQL_CACHE_SIZE      | Altera o php.ini 'pdo_mysql.cache_size' |
| PHP_PDO_MYSQL_DEFAULT_SOCKET  | Altera o php.ini 'pdo_mysql.default_socket' |
| PHP_SESSION_SAVE_HANDLER      | Altera o php.ini 'session.save_handler' |
| PHP_SESSION_SAVE_PATH         | Altera o php.ini 'session.save_path' |
| PHP_SESSION_USE_STRICT_MODE   | Altera o php.ini 'session.use_strict_mode' |
| PHP_SESSION_USE_COOKIES       | Altera o php.ini 'session.use_cookies' |
| PHP_SESSION_COOKIE_SECURE     | Altera o php.ini 'session.cookie_secure' |
| PHP_SESSION_NAME              | Altera o php.ini 'session.name' |
| PHP_SESSION_COOKIE_LIFETIME   | Altera o php.ini 'session.cookie_lifetime' |
| PHP_SESSION_COOKIE_PATH       | Altera o php.ini 'session.cookie_path' |
| PHP_SESSION_COOKIE_DOMAIN     | Altera o php.ini 'session.cookie_domain' |
| PHP_SESSION_COOKIE_HTTPONLY   | Altera o php.ini 'session.cookie_httponly' |
| PHP_XDEBUG_ENABLED            | Ativa o Xdebug... Adicione esse env e coloque um valor para habilitá-lo, pode ser true, On, ou qualquer outro valor. |

## Uso básico

Para usar esta imagem diretamente, você pode usar um arquivo docker-compose.yml para manter as coisas simples.

```yml
version: "2"
services:
  server:
    environment:
      - APACHE_SERVER_NAME=server.docker.localhost
      - PHP_ERROR_REPORTING=E_ALL
      - PHP_DISPLAY_ERRORS=On
      - PHP_HTML_ERRORS=On
      - PHP_XDEBUG_ENABLED=true
    volumes:
      - ./:/app
```

Depois só executar...

```bash
docker-compose up -d
```