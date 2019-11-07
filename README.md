# The Konou Vang Change Log

### Overview
Problems with MySQL 8 installation with Homebrew. This is a demonstration of how to downgrade to MySQL 5.7

https://medium.com/@at0dd/install-mysql-5-7-on-mac-os-mojave-cd07ec936034

Install MySQL 5.7 on macOS Mojave

This is a tutorial on how to install MySQL 5.7 on macOS since the default version of MySQL (at the time of writing) is 8.0. Some software like Sequel Pro don’t yet support the changes made in the newer version of MySQL.

First off, if you don’t have Homebrew installed, install it with:
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

Note: If you previously installed MySQL 8.0 but are downgrading, let’s uninstall everything first. This will completely remove any MySQL configurations and data that you might have.

brew uninstall mysql

brew uninstall mysql@5.7

rm -rf /usr/local/var/mysql

rm /usr/local/etc/my.cnf

Now lets install MySQL 5.7

brew install mysql@5.7

Since 5.7 isn’t the latest version of MySQL that Homebrew has available, we need to manually link it.

brew link --force mysql@5.7

Finally, if you want MySQL to always be running as a service, run:

brew services start mysql@5.7

or 

mysql -uroot

To make your installation a bit more secure, and to set the root password run the following command and fill out the options as you see fit.

mysql_secure_installation