# Documentation of project2
## Step1
a. I updated my server's package index then i installed Nginx
	
`sudo apt update`
    ![apt update](./images/image1.png)
    `sudo apt install nginx`
    ![Install nginx](./images/image2.png)

b. I verified that Nginx was successfully installed
    `sudo systemctl status nginx`
    ![Verify Nginx](./images/image3.png)

c. I accessed my server locally in my ubuntu shell
    `curl http://localhost:80`
    ![Access server](./images/image4.png)

d. I accessed my url using a web browser of my choice
    `http://<3.236.166.163>:80`
    ![Access server](./images/browser1.png)

## Step 2
a. I installed mysql server
   `sudo apt install mysql-server`
    ![Install Mysql](./images/image5.png)
    
b. I secured mysql installation
    `sudo mysql_secure_installation`
    ![Secure Mysql](./images/image6.png)

c. I tested if I was able to login to the Mysql console
    `sudo mysql`
    ![Login to Mysql](./images/image7.png)

d. I exit the Mysql console
    `mysql> exit`
    ![Exit Mysql](./images/image8.png)

## Step 3
 I installed php components
     `sudo apt install php-fpm php-mysql`
    ![Install php](./images/image9.png)

## Step 4
a. I created root web directory for my domain
   `sudo mkdir /var/www/projectLEMP`
    ![Sudo mkdir](./images/image10.png)

b. I assigned ownership of the directory
    `sudo chown -R $USER:$USER /var/www/projectLEMP`
    ![Sudo chown](./images/image11.png)

c. I opened a new configuration file
   `sudo nano /etc/nginx/sites-available/projectLEMP`
    ![Configuration file](./images/image12.png)

d. I activated my configuration by linking it to the configuration file from nginx
     `sudo ln -s /etc/nginx/sites-available/projectLEMP /etc/nginx/sites-enabled/`
    ![Configuration activation](./images/image13.png)
e. I tested my configuration for syntax error
    `sudo nginx -t`
    ![Configuration file](./images/image14.png)

f. I disabled the nginx host
   `sudo unlink /etc/nginx/sites-enabled/default`
   ![Disable host](./images/image15.png)

g. I reloaded nginx to apply the changes
    `sudo systemctl reload nginx`
    ![Reload nginx](./images/image16.png)

h. I opened the url on my web browser using my public ip address
     `http://<3.236.166.163>:80`
     ![web browser](./images/browser1.png)

## Step 5
a. I opened a new file in my text editor
   `sudo nano /var/www/projectLEMP/info.php`
   ![New file](./images/image17.png)

b. I pasted this lines in my new text editor file then i saved it and exit
   `<?php
phpinfo();`

c. I accessed this page in my web browser
   `http://`3.236.166.163`/info.php`
   ![php browser](./images/browser2.png)

d. I tried removing the file i created but it didn't work out. I tried troubleshooting but i still couldn't remove it.
   `sudo rm /var/www/your_domain/info.php`


## Step 6
a. I connected to mysql console
   `sudo mysql`
   ![mysql console](./images/image18.png)

b. I created a new database
   `mysql> CREATE DATABASE `graceful_database`;`
   ![graceful_database](./images/image19.png)

c. I created a new user
   `mysql>  CREATE USER 'graceful_user'@'%' IDENTIFIED WITH mysql_native_password BY 'password';`
   ![graceful_user](./images/image20.png)

d. I gave the user permission over the database
   `mysql> GRANT ALL ON graceful_database.* TO 'graceful_user'@'%';`
   ![Grant permission](./images/image21.png)

e. I exit the mysql shell
   `mysql> exit`
   ![Exit mysql](./images/image22.png)

f. Then, I tested if the new user have proper permission
   `mysql -u graceful_user -p`
   ![Test mysql](./images/image23.png)

g. I confirmed my access to the database
    `mysql> SHOW DATABASES;`
    ![show database](./images/image24.png)

h. Then I created a test-table named todo_list

    `CREATE TABLE example_database.todo_list (
mysql>     item_id INT AUTO_INCREMENT,
mysql>     content VARCHAR(255),
mysql>     PRIMARY KEY(item_id)
mysql> );`
    ![Test table](./images/image25.png)

i. I inserted a row of content in the test table
   `mysql> INSERT INTO graceful_database.todo_list (content) VALUES ("My first important item");`
   ![Insert row](./images/image26.png)

j. I confirmed that the data was successfully saved
    `mysql>  SELECT * FROM graceful_database.todo_list;`
    ![Confirm data](./images/image26.png)

k. I exit the mysql console
    `mysql> exit`
     ![Confirm data](./images/image27.png)

l. I created a php script that will connect to mysql
    `nano /var/www/projectLEMP/todo_list.php`
     ![php script](./images/image28.png)

m. I accessed the page in my web browser
   `http://<3.236.166.163>/todo_list.php`
   ![web browser](./images/browser3.png)










   




  





   



    

