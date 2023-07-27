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
$> docker-compose down 
~~~

To clean volumes: 
To start the Lamp stack: 
~~~bash:
$> docker volume prune
~~~
