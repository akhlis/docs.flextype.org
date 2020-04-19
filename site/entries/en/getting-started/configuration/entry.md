---
title: Configuration
description: Flextype allows you to configure your site in any way you can dream up, and it’s thanks to the powerful and flexible configuration options that make this possible.
breadcrumbs:
  0:
    title: "Documentation"
    link: "[site_url]/en/"
  1:
    title: "Basics"
    link: "[site_url]/en/basics/"
---
Flextype allows you to configure your site in any way you can dream up, and it’s thanks to the powerful and flexible configuration options that make this possible.

All Flextype configuration files are written in YAML syntax with a `.yaml` file extension. YAML is very intuitive which makes it very easy to both read and write.

You can update and create site configuration by editing file `/site/config/settings.yaml`

<div class="file-header"><i class="far fa-file-alt"></i> /site/config/settings.yaml</div>
```
# Set the timezone to be used on the website.
# For a list of valid timezone settings, see:
# http://php.net/manual/en/timezones.php
timezone: UTC

# Charset
#
# Set internal character encoding.
#
# Currently the following names are supported:
# http://php.net/manual/en/function.mb-regex-encoding.php#121645
charset: UTF-8

# The locale that'll be used by the Flextype.
#
# Available locales to use: flextype/config/locales.yaml
locale: en_US

# Application URL
#
# Define custom application url
url: ''

# Valid date format
#
# - date_format: Valid date format
#
# - date_display_format: Valid date format to display
#
# Date format variants:
#
# d-m-Y H:i" - 02-02-2020 09:41
# Y-m-d H:i" - 2020-02-02 09:41
# m/d/Y h:i a - 02/02/2020 09:41 pm
# H:i d-m-Y - 09:41 02-02-2020
# h:i a m/d/Y - 09:41 pm 02/02/2020
date_format: 'd-m-Y H:i'
date_display_format: 'd-m-Y H:i'

# Display errors
#
# Please make sure to set false for error `display` in production!
#
# Displaying PHP errors on a public server can be a serious security risk:
#
# - Error messages are displayed with detailed information about the code structure (e.g. file path, class, method)
# - With Whoops enabled, there will be even more detailed information about the code structure
# - Detailed error messages for login failures could leak information to attackers
#
# In a production environment, always log errors to your PHP error logs.
#
# - display: Display errors or not.
errors:
  display: false

# Cache
#
# - enabled:         Set to true to enable caching
#
# - prefix:          Cache prefix string (prevents cache conflicts)
#
# - driver:          Available drivers: auto (will get one from installed cache drivers), apcu,
#                    apc, array, wincache, xcache, memcache, memcached, redis, file.
#
# - lifetime:        Lifetime of cached data in seconds
#
# - redis.socket:    Path to redis unix socket (e.g. /var/run/redis/redis.sock),
#                    false = use server and port to connect
#
# - redis.password   Redis password
#
# - redis.server     Redis server
#
# - redis.port       Redis port
#
# - memcache.server  Memcache server
#
# - memcache.port    Memcache port
#
# - memcached.server Memcached server
#
# - memcached.port   Memcached port
#
# - sqlite3.database SQLite3 Database
#
# - sqlite3.table    SQLite3 Table
cache:
  enabled: true
  prefix: flextype
  driver: auto
  lifetime: 604800
  memcache:
    server: localhost
    port: 11211
  memcached:
    server: localhost
    port: 11211
  redis:
    socket: false
    password: false
    server: localhost
    port: 6379
  sqlite3:
    database: flextype
    table: flextype

# Whoops
#
# Error handler framework for PHP.
#
# - editor: emacs, idea, macvim, phpstorm, sublime, textmate, xdebug, vscode, atom, espresso
#
# - page_title: page title
whoops:
  editor: atom
  page_title: Error!

# Slim
#
# - display_error_details: When true, additional information about exceptions are
#                          displayed by the default error handler.
#
# - add_content_length_header: When true, Slim will add a Content-Length header to
#                              the response. If you are using a runtime analytics tool,
#                              such as New Relic, then this should be disabled.
#
# - router_cache_file: Filename for caching the FastRoute routes. Must be set to
#                      a valid filename within a writeable directory. If the file
#                      does not exist, then it is created with the correct cache
#                      information on first run. Set to false to disable the FastRoute
#                      cache system.
#
# - determine_route_before_app_middleware: When true, the route is calculated before
#                                          any middleware is executed. This means that you
#                                          can inspect route parameters in middleware if you need to.
#
# - output_buffering: If false, then no output buffering is enabled.
#                     If 'append' or 'prepend', then any echo or print statements
#                     are captured and are either appended or prepended to the Response
#                     returned from the route callable.
#
# - response_chunk_size: Size of each chunk read from the Response body when sending to the browser.
#
# - http_version: The protocol version used by the Response object.
display_error_details: false
add_content_length_header: true
router_cache_file: false
determine_route_before_app_middleware: false
output_buffering: append
response_chunk_size: 4096
http_version: '1.1'

# Slugify
#
# - separator: By default Slugify will use dashes as separators.
#              If you want to use a different default separator,
#              you can set the separator option.
#
# - lowercase: By default Slugify will convert the slug to lowercase.
#              If you want to preserve the case of the string you can set the
#              lowercase option to false.
#
# - trim:      By default Slugify will remove leading and trailing separators before
#              returning the slug. If you do not want the slug to be trimmed you can
#              set the trim option to false.
#
# - regexp:    You can also change the regular expression that is used to replace
#              characters with the separator.
#
# - lowercase_after_regexp: Lowercasing is done before using the regular expression.
#                           If you want to keep the lowercasing behavior but your
#                           regular expression needs to match uppercase letters,
#                           you can set the lowercase_after_regexp option to true.
#
# - strip_tags: Adds in an option to go through strip_tags() in case the string contains HTML etc.
slugify:
  separator: "-"
  lowercase: true
  trim: true
  regexp: "/[^A-Za-z0-9]+/"
  lowercase_after_regexp: false
  strip_tags: false

# Image
#
# - driver: gd or imagick
image:
  driver: gd

# API's
api:
  delivery:
    images:
      enabled: true
      default_token:
    entries:
      enabled: true
      default_token:
    registry:
      enabled: true
      default_token:
  management:
    entries:
      enabled: true
      default_token:
```
