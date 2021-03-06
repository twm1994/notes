initialize mysql

first cd to basedir

`bin\mysqld --initialize`

start and stop the server
```cmd
"full\path\to\basedir\bin\mysqld" --console
NET START MySQL
NET STOP MySQL
mysqladmin shutdown
```

connect to the server

`cd` to basedir 
`bin\mysql -u root -p`

assign new password

`ALTER USER 'root'@'localhost' IDENTIFIED BY 'new_password';`

connect to specific database when starting a mysql session

`mysql -u root -p dbname`

version verification

`bin\mysqladmin -u root -p version`

shutdown verification

`bin\mysqladmin -u root -p shutdown`

jdbc connection parameters

`jdbc:mysql://localhost/dbname?useLegacyDatetimeCode=false&serverTimezone=Asia/Hong_Kong`

## config mysql on linux
### disable starting on boot

`sudo systemctl disable mysql`

### setup root user

`sudo mysql_secure_installation`

### move data dir
```sh
mkdir mysql-data
chown -R  mysql:mysql mysql-data
sudo service mysql stop
```

### check current data dir, default is /var/lib/mysql

`sudo mysql -u root -p -e "select @@datadir;"`

### move all data and perserve permissions and timestamps will move all files to {datadir}/mysql

`sudo rsync -av /var/lib/mysql {datadir}`

### rename original dir to avoid confusion

`sudo mv /var/lib/mysql /var/lib/mysql.bak`

### change datadir in the following config file

`sudo vim /etc/mysql/mysql.conf.d/mysqld.cnf`

### configure apparmor
`sudo vim /etc/apparmor.d/tunables/alias`

### uncomment the alias line and changedatadir
```sh
alias /var/lib/mysql -> {datadir}/mysql
sudo systemctl restart apparmor
```

### add dir to pass environment check

`sudo mkdir /var/lib/mysql/mysql -p`

restart mysql and check status

### remove sudo login

`sudo mysql -u root -p`

### mysql query
```sql
drop user 'root'@'localhost';
create user 'root'@'localhost' identified with mysql_native_password by 'password';
grant all privileges on *.* to 'root'@'%' with grant option;
flush privileges;
```

### heck password

`sudo cat /etc/mysql/debian.cnf`

### check user

`select user,host,plugin from mysql.user;`
