![CiS Compliant](https://img.shields.io/badge/cis-compliant-brightgreen)
[![Apache License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](LICENSE)
![GitHub release (latest by date)](https://img.shields.io/github/v/release/OT-OSM/mysql)

# OSM: MySQL

A high end ansible role to setup standalone or a cluster MySQL with best practices in terms of security and performance tunning.

## Key Features

- [X] CIS compliant
- [X] Best Practices(Performance Tunning)
- [X] Database and User Management

## Requirements

No special requirement, only root access of the server is required.

## Role Variables

We have categorized variables into two part i.e. **[Manadatory]()** and **[Optional]()**

#### Mandatory Variables

|**Variable**|**Default Value**|**Possible Values**|**Description**|
|------------|-----------------|-------------------|---------------|
|mysql_root_username| `root` | *Root Username* | Name of the admin user of MySQL |
|mysql_root_password| `N0Tweak$_@123!` | *Any Strong Password* | A strong password for MySQL root user |
|mysql_replication_user.user | `slave` | *Any Username* | Name of the slave user |
|mysql_replication_user.password | `N0Tweak$_@123!` | *Any Strong Password* | A strong password for MySQL Slave |
|mysql_install_packages | `true` | true or false | Whether you want to install MySQL packages. Set the value false if you need only configuration part |
|replication | `true` | true or false | If you don't want to setup slave, set the value false |
|users_creation | `true` | true or false | Whether you want to include tasks for user creation or not |
|database_creation | `true` | true or false | Whether you want to include tasks for database creation or not |

#### Optional Variables

|**Variable**|**Default Value**|**Possible Values**|**Description**|
|------------|-----------------|-------------------|---------------|
|mysql_config_file| `/etc/mysql/my.cnf` | *Any Linux Path* | Configuration file location of MySQL |
|mysql_slow_query_log_file | `/var/log/mysql/mysql-slow.log` | *Any Linux Path* | Log file location of MySQL slow query |
|mysql_log_error | `/var/log/mysql/mysql.err` | *Any Linux Path* | Log file location of MySQL errors |
|mysql_max_binlog_size | `100M` | *Size in MB* | Maximum size of bin log files in MySQL |
|mysql_binlog_format | `MIXED` | ROW or COLOUMN or MIXED | Binlog format of MySQL |
|debian_mysql_version | 5.7 | *Any MySQL Version* | Which version of MySQL you want to install on Debian System |
|mysql_redhat_version | el7 | *Any MySQL Version* | Which version of MySQL you want to install on RedHat System |

The rest of the things are in [defaults](./defaults/main.yml)

## Inventory

An example inventory could be like this:-

```ini
[master]
master_server1

[slave]
slave_server1

[mysql]
master_server1
slave_server1

[mysql_cluster:children]
mysql
master
slave

[mysql_cluster:vars]
ansible_user=ubuntu
```

Leave blank `master` and `slave` if you don't want Master-Slave setup.

## Example Playbook

Here is an example of playbook to execute this role:-

```yaml
---
- hosts: mysql_cluster
  roles:
    - role: osm_mysql
      become: yes
```

## Usage

There are multiple ways of executing the playbook according to your environment

- To run complete role

```shell
ansible-playbook -i hosts site.yml
```

- To create users

```shell
ansible-playbook -i hosts site.yml --tags "create_user"
```

- To create databases

```shell
ansible-playbook -i hosts site.yml --tags "create_database"
```

## Running Test Cases for Setup and CIS Benchmarks

For running the test cases, we have a seperate folder named [inspec](./inspec). Inspec (https://www.inspec.io/) should be installed if you want to run the test cases.

Command which needs to be run

```shell
inspec exec . -t ssh://username@server_ip -i /path/to/keyfile
```

For further test results information, you can go through the [README.md](./inspec/README.md) of inspec profile.

## References

Here we do have some of our OpsTree blog's regarding MySQL.

https://blog.opstree.com/2019/03/26/stay-away-replication-lag/

https://blog.opstree.com/2019/07/23/mysql-monitoring/

https://blog.opstree.com/2019/09/24/mysql-data-at-rest-encryption/

https://blog.opstree.com/2018/12/11/setting-up-mysql-monitoring-with-prometheus/

## Author

**[Abhishek Dubey](abhishek.dubey@opstree.com)**

## To Do

- [ ] Enable SSL communication between master and slave
