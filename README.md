# EJBCA deployment playbook

This playbook is planned to run on a Centos/RHEL 7 server.

## host file

It contains the servers where to run the playbook. By default, it will run on the server **centos3**.

``` yaml
[all:children]
ca_server

[ca_server]
centos3
```

## Package download server

It's not possible to download directly EJBCA package so a solution is to setup a downlaod server with the following packages:

- ejbca_ce_6_5.0.5.zip
- mariadb-java-client-1.5.8.jar
- wildfly-10.1.0.Final.zip

Else you can skip the tag **download** and put the packages directly in the **ejbca_download_dir** directory.


## Variables

All variables are stored in the **group_vars/all** file.
This playbook store passwords in clear text but it can be easily modified to store them in an encrypted file with **ansible-vault**.

## Run playbook

```
ansible-playbook -i hosts main.yml
```

Copyright
==========

The code is licensed as GNU AGPLv3. See the LICENSE file for the full license.

Copyright (c) 2017 Alain Dejoux <adejoux@djouxtech.net>