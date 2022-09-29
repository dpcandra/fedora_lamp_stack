# fedoralamp
How to install LAMP stack on Fedora

Click this link to see full page

https://github.com/dpcandra/fedoralamp/wiki/How-To-install-LAMP-Fedora-(Development-purposes)


Welcome to the fedoralamp wiki!

Follow This step to able to install LAMP stack for development purposes on Fedora Linux

    Disable SElinux Firewall if SeLinux enable you want able to open project from another computer or downloaded project open file /etc/selinux/config with text editor find SELINUX=enforcing and change to SELINUX=disabled

    Install Apache $ sudo dnf install httpd

$ sudo systemctl enable httpd.service

$ sudo systemctl start httpd.service

after install you can enable and start the service using systemd. Disable the open port for forbid another people accessing your computer edit apache conf file /etc/httpd/conf/httpd.conf find Listen 80 and change it into Listen 127.0.0.1:80

if there any error on config file you can check using $ sudo systemctl status httpd.service to see the service is running normally/error

Open Localhost in the browser you should see the Fedora Apache Landing page

The root directory by default /var/www/html

To able write in root folder you can change user and access to the html folder $ sudo chown -R user:user , $ sudo chmod -R 775 /foldername flag -R mean apply everything in that folder item/subfolder

    Install php $ sudo dnf install php

$ sudo dnf install php-cli

$ sudo dnf install php-mysqli

after installing php check the php version installed on the terminal $ php -v

to check php is working properly create new file for example index.php , and insert this code <?php phpinfo(); ?>

To displaying ERROR message , edit file /etc/php.ini find this code display_errors = Off to display_errors = On

Install XDEBUG *optional $ sudo dnf install php-xdebug , xdebug extension already attached on php.ini don't need to edit the config. all you need to do is restart the service $ sudo systemctl restart httpd.service
