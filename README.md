# vagrant-boxes
A vagrant box that provisions Oracle Database automatically, using Vagrant, an Oracle Linux 7.3 box and a shell script.

## Prerequisites
1. Install [Oracle VM VirtualBox](https://www.virtualbox.org/wiki/Downloads)
2. Install [Vagrant](https://vagrantup.com/)

## Getting started
1. Clone this repository `git clone https://github.com/gvenzl/vagrant-boxes`
2. Change into the desired version folder
3. Download the installation zip files from OTN into this folder - first time only:
[http://www.oracle.com/technetwork/database/enterprise-edition/downloads/index.html](http://www.oracle.com/technetwork/database/enterprise-edition/downloads/index.html)
4. Run `vagrant up`
   1. The first time you run this it will provision everything and may take a while. Ensure you have a good internet connection!
   2. The Vagrant file allows for customization, if desired (see [Customization](#customization))
5. Connect to the database.
6. You can shut down the box via the usual `vagrant halt` and the start it up again via `vagrant up`.

## Connecting to Oracle
* Hostname: `localhost`
* Port: `1521`
* SID: `ORCLCDB`
* PDB: `ORCLPDB1`
* OEM port: `5500`
* All passwords are `password`

## Acknowledgements
Based on:
@steveswinsburg's work here: https://github.com/steveswinsburg/oracle12c-vagrant  
@totalamateurhour's work here: https://github.com/totalamateurhour/oracle-12.2-vagrant

## Other info

* If you need to, you can connect to the machine via `vagrant ssh`.
* You can `sudo su - oracle` to switch to the oracle user.
* The Oracle installation path is `/opt/oracle/` by default.
* On the guest OS, the directory `/vagrant` is a shared folder and maps to wherever you have this file checked out.

### Customization
You can customize your Oracle environment by amending the environment variables in the `Vagrantfile` file.
The following can be customized:
* `ORACLE_BASE`: `/opt/oracle/`
* `ORACLE_HOME`: `/opt/oracle/product/12.2.0.1/dbhome_1`
* `ORACLE_SID`: `ORCLCDB`
* `ORACLE_PDB`: `ORCLPDB1`
* `ORACLE_CHARACTERSET`: `AL32UTF8`
* `ORACLE_EDITION`: `EE` | `SE2`

## Known issues
None.
