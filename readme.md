# Apache Lamp stack with MariaDB


## Description
This folders collection contains different LAMP stack. Each one is a different PHP version from 7.2 to 8.2.
The database is always MariaDB in the latest version.
The PHPMyAdmin is always in the latest version too. 
An index.php file is located in the www folder so you can easily check the Lamp version which is running. 


## How it works?
- The Webserver port on the host is 80 (standard) => http://localhost
- The PHPMyAdmin is accessible with http://localhost:1200


## Useful commands
You have to be located at the root folder of the php Lamp stack you want to run, open a terminal and then launch the following commands: 

To start the Lamp stack: 
~~~bash:
$> docker-compose up -d 
~~~

To stop the Lamp stack: 
~~~bash:
$> docker-compose down -v
~~~

To clean volumes: 
To start the Lamp stack: 
~~~bash:
$> docker volume prune
~~~

## Common errors
### This PHP doesn't load any modules !
Yes! This is true. I got the experience while I was trying to test a Wordpress website locally. 
The php:x.y-apache (with x.y major and minor version numbers) image is coming with Apache2 and PHP only. Then if you try to connect a database or resize an image, you'll get a beautiful error message. 
That's why I added an apache folder with a Dockerfile which provides an Apache2 server with PHP and some required modules already installed. In fact, this version is inspired from the official wordpress Dockerfile image. 
I created it only in the __php8.2__ folder and I updated the docker-compose.yml accordingly.

### PHPMyAdmin refuses to import my SQL dump
There is a limitation concerning the Post request size. I added the __'UPLOAD_LIMIT: 300M'__ parameter for the phpmyadmin part of the docker-compose.yml file. This parameter is in comment but you can uncomment it if you encounter this kind of error while trying to import your (hume) dump file. 

