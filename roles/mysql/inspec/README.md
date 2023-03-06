## CIS Results

```
Profile: CIS baseline for MySQL (mysql-cis-baseline)
Version: 0.1.0
Target:  local://

  ✔  2.3: Do Not Reuse User Accounts (Not Scored)
     ✔  Mysql database user: monitoring is expected to be in "root"
     ✔  Mysql database user: slave is expected to be in "root"
     ✔  Mysql database user: example is expected to be in "root"
     ✔  Mysql database user: slave is expected to be in "root"
     ✔  Mysql database user: debian-sys-maint is expected to be in "root"
     ✔  Mysql database user: mysql.session is expected to be in "root"
     ✔  Mysql database user: mysql.sys is expected to be in "root"
     ✔  Mysql database user: root is expected to be in "root"
  ✔  4.5: Ensure 'mysqld' Is Not Started with '--skip-grant-tables' (Scored)
     ✔  File /etc/mysql/my.cnf content is expected to match "skip-grant-tables"
  ✔  1.1: 1.1 Place Databases on Non-System Partitions (Scored)
     ✔  The mysql data directory partition installed on is expected not to include "/"
     ✔  The mysql data directory partition installed on is expected not to include "/var"
     ✔  The mysql data directory partition installed on is expected not to include "/usr"
  ✔  5.3: Ensure 'process_priv' Is Not Set to 'Y' for Non-Administrative Users (Scored)
     ✔  The mysql user: root with process_priv is expected to be in "root"
     ✔  The mysql user: debian-sys-maint with process_priv is expected to be in "root"
  ✔  3.2: Ensure 'log_bin_basename' Files Have Appropriate Permissions and Ownership (Scored)
     ✔  Directory /var/lib/mysql/mysql-bin is expected to exist
     ✔  Directory /var/lib/mysql/mysql-bin owner is expected to eq "mysql"
     ✔  Directory /var/lib/mysql/mysql-bin group is expected to eq "mysql"
     ✔  Directory /var/lib/mysql/mysql-bin mode is expected to be <= 432
  ✔  7.2: Ensure 'secure_auth' is set to 'ON' (Scored)
     ✔  The MySQL secure_auth is expected to cmp == 1
  ✔  7.8: Ensure No Anonymous Accounts Exist (Scored)
     ✔  The MySQL anonymous accounts that exist is expected to be empty
  ✔  4.3: Ensure 'allow-suspicious-udfs' Is Set to 'FALSE' (Scored)
     ✔  MySQL Configuration allow-suspicious-udfs is expected to be nil
     ✔  Command: `ps aux | grep mysql` stdout is expected not to match "allow-suspicious-udfs"
  ✔  7.1: Ensure 'old_passwords' Is Not Set to '1' (Scored)
     ✔  The MySQL old_passwords is expected not to cmp == 1
  ✔  9.5: Ensure No Replication Users Have Wildcard Hostnames (Scored)
     ✔  The replication users with the super_priv not set to Y is expected to be empty
  ✔  4.8: Ensure 'secure_file_priv' Is Not Empty (Scored)
     ✔  The secure_file_priv variable is expected not to be empty
  ✔  7.3: Ensure Passwords Are Not Stored in the Global Configuration (Scored)
     ✔  MySQL Configuration client.password is expected to be nil
  ✔  6.1: Ensure 'log_error' Is Not Empty (Scored)
     ✔  The MySQL log_error is expected not to be empty
  ✔  5.4: Ensure 'super_priv' Is Not Set to 'Y' for Non-Administrative Users (Scored)
     ✔  The mysql user: root with super_priv is expected to be in "root"
     ✔  The mysql user: mysql.session with super_priv is expected to be in "root"
     ✔  The mysql user: debian-sys-maint with super_priv is expected to be in "root"
  ✔  5.5:  Ensure 'shutdown_priv' Is Not Set to 'Y' for Non-Administrative Users (Scored)
     ✔  The mysql user: root with shutdown_priv is expected to be in "root"
     ✔  The mysql user: debian-sys-maint with shutdown_priv is expected to be in "root"
  ↺  2.4: Do Not Use Default or Shared Cryptographic Material (Not Scored)
     ↺  A manual review is required to ensure the default or shared cryptographic material is not being used
  ✔  1.2: Use Dedicated Least Privileged Account for MySQL Daemon/Service (Scored)
     ✔  The user runnning the MySQL Daemon/Service is expected to cmp == "mysql"
  ✔  3.5: Ensure 'relay_log_basename' Files Have Appropriate Permissions and Ownership (Scored)
     ✔  Directory /var/lib/mysql/ip-172-31-90-2-relay-bin is expected to exist
     ✔  Directory /var/lib/mysql/ip-172-31-90-2-relay-bin owner is expected to eq "mysql"
     ✔  Directory /var/lib/mysql/ip-172-31-90-2-relay-bin group is expected to eq "mysql"
     ✔  Directory /var/lib/mysql/ip-172-31-90-2-relay-bin mode is expected to be <= 432
  ↺  2.1: Dedicate Machine Running MySQL (Not Scored)
     ↺  A manual review is required to verfify a dedicated machine is running MySQL
  ✔  7.4: Ensure 'sql_mode' Contains 'NO_AUTO_CREATE_USER' (Scored)
     ✔  The MySQL global sql mode is expected to include "NO_AUTO_CREATE_USER"
     ✔  The MySQL session sql mode is expected to include "NO_AUTO_CREATE_USER"
  ✔  3.3: Ensure 'log_error' Has Appropriate Permissions and Ownership (Scored)
     ✔  File /var/log/mysql/mysql.err is expected to exist
     ✔  File /var/log/mysql/mysql.err owner is expected to eq "mysql"
     ✔  File /var/log/mysql/mysql.err group is expected to eq "mysql"
     ✔  File /var/log/mysql/mysql.err mode is expected to be <= 432
  ✔  3.4: Ensure 'slow_query_log' Has Appropriate Permissions and Ownership (Scored)
     ✔  File /var/log/mysql/mysql-slow.log is expected to exist
     ✔  File /var/log/mysql/mysql-slow.log owner is expected to eq "mysql"
     ✔  File /var/log/mysql/mysql-slow.log group is expected to eq "mysql"
     ✔  File /var/log/mysql/mysql-slow.log mode is expected to be <= 432
  ✔  6.4: Ensure 'log-raw' Is Set to 'OFF' (Scored)
     ✔  File /etc/mysql/my.cnf content is expected to match "log-raw"
  ✔  7.5: Ensure Passwords Are Set for All MySQL Accounts (Scored)
     ✔  The MySQL users with blank passwords is expected to be empty
  ✔  4.9: Ensure 'sql_mode' Contains 'STRICT_ALL_TABLES' (Scored)
     ✔  The sql_mode is expected to include "STRICT_ALL_TABLES"
  ✔  5.8: Ensure 'repl_slave_priv' Is Not Set to 'Y' for Non-Slave Users (Scored)
     ✔  The mysql user: root with repl_slave_priv is expected to be in "root"
     ✔  The mysql user: debian-sys-maint with repl_slave_priv is expected to be in "root"
     ✔  The mysql user: slave with repl_slave_priv is expected to be in "root"
     ✔  The mysql user: slave with repl_slave_priv is expected to be in "root"
  ✔  7.7: Ensure No Users Have Wildcard Hostnames (Scored)
     ✔  The MySQL users that have Wildcard Hostnames is expected to be empty
  ✔  4.6: Ensure '--skip-symbolic-links' Is Enabled (Scored)
     ✔  File /etc/mysql/my.cnf content is expected to match "skip-symbolic-links"
  ✔  5.2: Ensure 'file_priv' Is Not Set to 'Y' for Non-Administrative Users (Scored)
     ✔  The mysql user: root with file_priv is expected to be in "root"
     ✔  The mysql user: debian-sys-maint with file_priv is expected to be in "root"
  ✔  5.7: Ensure 'grant_priv' Is Not Set to 'Y' for Non-Administrative Users (Scored)
     ✔  The mysql user: root with grant_priv access in the mysql.user table is expected to be in "root"
     ✔  The mysql user: debian-sys-maint with grant_priv access in the mysql.user table is expected to be in "root"
  ✔  1.4: Verify that 'MYSQL_PWD' Is Not Set (Scored)
     ✔  The MYSQL_PWD environment variable is expected to eq ""
  ✔  4.1: 4.1 Ensure Latest Security Patches Are Applied (Not Scored)
     ✔  The mysql version installed is expected to cmp >= "5.7.24-enterprise-commercial-advanced"
  ↺  9.1: Ensure Replication Traffic Is Secured (Not Scored)
     ↺  A manual review is required to ensure the replication traffic is secured
  ✔  9.4: Ensure 'super_priv' Is Not Set to 'Y' for Replication Users (Scored)
     ✔  The replication users with the super_priv not set to Y is expected to be empty
  ✔  1.5: Disable Interactive Login (Scored)
     ✔  /etc/passwd with user == "mysql" shells is expected to cmp == "/bin/false"
  ✔  9.3: Ensure 'master_info_repository' Is Set to 'TABLE' (Scored)
     ✔  The master_info_repository is expected to cmp == "TABLE"
  ✔  3.1: Ensure 'datadir' Has Appropriate Permissions and Ownership (Scored)
     ✔  Directory /var/lib/mysql is expected to exist
     ✔  Directory /var/lib/mysql owner is expected to eq "mysql"
     ✔  Directory /var/lib/mysql group is expected to eq "mysql"
     ✔  Directory /var/lib/mysql mode is expected to be <= 448
  ✔  4.4: Ensure 'local_infile' Is Disabled (Scored)
     ✔  The MySQL local_infile setting is expected to cmp == 0
  ✔  6.10: Ensure audit_log_statement_policy is set to ALL (Scored)
     ✔  The MySQL log_error is expected not to be empty
  ✔  4.2: Ensure the 'test' Database Is Not Installed (Scored)
     ✔  The check wether the test database is installed is expected to be empty
  ✔  6.3: Ensure 'log_warnings' Is Set to '2' (Scored)
     ✔  The MySQL log_warnings is expected to cmp == 2
  ✔  8.1: Ensure 'have_ssl' Is Set to 'YES' (Scored)
     ✔  The MySQL have_ssl variable is expected to cmp == "YES"
  ✔  7.6: Ensure Password Policy Is in Place (Scored)
     ✔  The MySQL validate_password_length variable is expected to cmp >= 14
     ✔  The MySQL validate_password_mixed_case_count variable is expected to cmp >= 1
     ✔  The MySQL validate_password_number_count variable is expected to cmp >= 1
     ✔  The MySQL validate_password_special_char_count variable is expected to cmp >= 1
     ✔  The MySQL validate_password_policy variable is expected to cmp == "STRONG"
     ✔  File /etc/mysql/my.cnf content is expected to match "validate_password.so"
     ✔  File /etc/mysql/my.cnf content is expected to match "FORCE_PLUS_PERMANENT"
  ✔  3.8: Ensure Plugin Directory Has Appropriate Permissions and Ownership (Scored)
     ✔  Directory /usr/lib/mysql/plugin/ is expected to exist
     ✔  Directory /usr/lib/mysql/plugin/ owner is expected to eq "mysql"
     ✔  Directory /usr/lib/mysql/plugin/ group is expected to eq "mysql"
     ✔  Directory /usr/lib/mysql/plugin/ mode is expected to be <= 509
  ✔  3.6: Ensure 'general_log_file' Has Appropriate Permissions and Ownership (Scored)
     ✔  Directory /var/lib/mysql/ip-172-31-90-2.log is expected to exist
     ✔  Directory /var/lib/mysql/ip-172-31-90-2.log owner is expected to eq "mysql"
     ✔  Directory /var/lib/mysql/ip-172-31-90-2.log group is expected to eq "mysql"
     ✔  Directory /var/lib/mysql/ip-172-31-90-2.log mode is expected to be <= 432
  ✔  4.7: Ensure the 'daemon_memcached' Plugin Is Disabled (Scored)
     ✔  The daemon_memcached plugins installed is expected to be empty
  ✔  6.2: Ensure Log Files Are Stored on a Non-System Partition (Scored)
     ✔  The mysql log files partition installed on is expected not to include "/"
     ✔  The mysql log files partition installed on is expected not to include "/var"
     ✔  The mysql log files partition installed on is expected not to include "/usr"


Profile Summary: 44 successful controls, 0 control failures, 3 controls skipped
Test Summary: 93 successful, 0 failures, 3 skipped
```
