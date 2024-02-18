# COMPLETE USER REGISTRATION SYSTEM USING LAMP #
   In this tutorial, I walk through the complete process of creating a user registration system using LAMP circuit. I will also show you how you can make some pages accessible only to logged-in users.
## The first thing we all need to do install apche server
firstly update the cli using command
  $ sudo apt update
now install apache server
  $ sudo apt install apache2
now start and enable server
  $ sudo systemctl start apache2
  $ sudo systemctl enable apache2
after this check the server is running or not : go to the web browser and paste the ip address or localhost
  http://localhost.com
  http://ipaddress.com
 if server configration  is ok its show default server page
## Now install the php server and module which is required to create coneection
  $ sudo apt install php
for installing module
  $ sudo apt install libapache-mod-php php-mysql
## Now install mysql for database creation
  $ sudo apt install mysql-server
  After installation we need to create a database called registratoin. In this database, add a table called persons. The persons table will take the following four fields
   id
   username
   email
   password
To create the database we need to crete a user and table
 enter in mysql we use - sudo mysql
 after enter in mysql we create a database
   CREATE DATABASE registration;
 now create a user and give it permission to access database
   CREATE USER 'user'@'%' IDENTIFIED WITH mysql_native_password BY 'q123';
 to give all privilege
   GRANT ALL PRIVILEGES ON registration.* TO 'user'@'%';
   FLUSH PRIVILEGES;
   EXIT;
 Now enter through user and create a table 
   mysql -u user -p
 after enter this command give the password which we create
  now enter in database
    USE registration;
   now create a table 
    CREATE TABLE person ( id int(100) NOT NULL AUTO_INCREMENT PRIMARY KEY,
                          username varchar(20) NOT NULL,
                          email varchar(50) NOT NULL,
                          password varchar(100) NOT NULL );
   that,s it with database.
now create a folder called user in a directory accessible to our server.
 the path of directory 
   $ cd /var/www
 create a folder user 
   $ sudo mkdir user
 now enter this folder and create following files
   index.php, error.php, login.php, server.php, style.css, register.php
## Registration a user
### open the register.php file and paste the following code in it
                      
