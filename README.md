**Status: DEV**

Microservices VM
================

Deploys a minimal [Microservices](http://en.wikipedia.org/wiki/Microservices) platform to a UNIX VM to enable services to be deployed using [pio](https://github.com/pinf-io/io.pinf.pio).


Architecture
------------

  * **Client Tooling** - All interaction with a VM happens using [pio](https://github.com/pinf-io/io.pinf.pio) and is supported for clients running on:

    * OSX
    * Ubuntu

  * Supported **Operating Systems** for VMs:

    * Ubuntu

  * **Request Processing** - All socket requests can get routed through the following stack:

    * **Global Proxy** - NodeJS-based for dynamic routing.
      * Static Filesystem
      * NodeJS processes
      * [nginx](http://nginx.org/)
        * Static Filesystem
        * NodeJS processes
        * [PHP-FPM](http://php.net/manual/en/install.fpm.php)
        * [Apache](http://httpd.apache.org/)
          * Static Filesystem
          * NodeJS processes
          * [mod_php](http://php.net/manual/en/security.apache.php)

  * **Server-Side Scripting** - All services are called from a [bash.origin](https://github.com/bash-origin/bash.origin)-based environment that provides:

    * **Global Registry** - Stores arbitrary assets and links in a filesystem common to all services.

    * **Service Containers** - Plugin-based conventions, environment variables and tools to deploy services into namespace-isolated containers.

    * **Service Languages** - Programming languages and their package installers:

      * [NodeJS](http://nodejs.org)
        * [npm](http://npmjs.org)
      * [PHP](http://php.net)
        * [Composer](https://getcomposer.org/)


Usage
=====

*TODO*


Provenance
==========

This project extends [github.com/pinf-tools/ScriptedCloud](https://github.com/pinf-tools/ScriptedCloud) and adds original source logic [UNLICENSED](http://unlicense.org/) by [Christoph Dorn](http://christophdorn.com).
