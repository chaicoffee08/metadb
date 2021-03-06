metadb
======

## Installation

### Vagrant VM

The easiest way to start is to setup ready-to-use [Vagrant](https://www.vagrantup.com/)
VM. To do that [download](https://www.vagrantup.com/downloads.html) and install
Vagrant for your OS. Then copy the config files:

1. `config.py.sample` to `config.py` *(you don't need to modify this file)*

After that you can spin up the VM and start working with it:

    $ vagrant up

There are some environment variables that you can set to affect the
provisioning of the virtual machine.

 * `MDB_NCPUS`: Number of CPUs to put in the VM (default 1)
 * `MDB_MEM`:   Amount of memory (default 1024mb)
 * `MDB_MIRROR`: ubuntu mirror (default archive.ubuntu.com)

You can start the web server (will be available at http://127.0.0.1:8080/):

    $ vagrant ssh
    $ cd metadb
    $ python manage.py runserver

There are some shortcuts defined using fabric to perform commonly used
commands:

 * `fab vpsql`: Load a psql session. Requires a local psql client
 * `fab vssh`: Connect to the VM more efficiently, saving the settings
               so that you don't need to run vagrant each time you ssh.
