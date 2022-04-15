# Documentation of project2
## Step1
a. I updated my server's package index then i installed Nginx
	
`sudo apt update`
    ![apt update](\images\image1.png)
    `sudo apt install nginx`
    ![install nginx](\images\image2.PNG)

b. I verified that Nginx was successfully installed
    `sudo systemctl status nginx`
    ![Status](\images\image3.PNG)


c. I accessed my server locally in my ubuntu shell
    `curl http://localhost:80`
    ![Access server](\images\image4.PNG)


d. I accessed my url using a web browser of my choice
    `http://<3.236.166.163>:80`
    ![Access server](\images\browser1.PNG)

## Step 2
a. I installed mysql server
   `sudo apt install mysql-server`
    ![install mysql](\images\image5.PNG)

    
b. I secured mysql installation
    `sudo mysql_secure_installation`
    ![Secure nginx](\images\image6.PNG)


c. I tested if I was able to login to the Mysql console
    `sudo mysql`
    ![login to mysql](\images\image7.PNG)


d. I exit the Mysql console
    `mysql> exit`
    ![exit mysql](\images\image8.PNG)


## Step 3
 I installed php components
     `sudo apt install php-fpm php-mysql`
    ![install php](\images\image9.PNG)


## Step 4
a. I created root web directory for my domain
   `sudo mkdir /var/www/projectLEMP`
    ![sudo mkdir](\images\image10.PNG)


b. I assigned ownership of the directory
    `sudo chown -R $USER:$USER /var/www/projectLEMP`
    ![sudo chown](\images\image11.PNG)



c. I opened a new configuration file
   `sudo nano /etc/nginx/sites-available/projectLEMP`
    ![configuration file](\images\image12.PNG)


d. I activated my configuration by linking it to the configuration file from nginx
     `sudo ln -s /etc/nginx/sites-available/projectLEMP /etc/nginx/sites-enabled/`
    ![configuration activation](\images\image13.PNG)

e. I tested my configuration for syntax error
    `sudo nginx -t`
    ![configuration file](\images\image14.PNG)


f. I disabled the nginx host
   `sudo unlink /etc/nginx/sites-enabled/default`
  ![disable host](\images\image15.PNG)


g. I reloaded nginx to apply the changes
    `sudo systemctl reload nginx`
    ![reload nginx](\images\image16.PNG)


h. I opened the url on my web browser using my public ip address
     `http://<3.236.166.163>:80`
     ![web browser](\images\browser1.PNG)

## Step 5
a. I opened a new file in my text editor
   `sudo nano /var/www/projectLEMP/info.php`
  ![new file](\images\image17.PNG)


b. I pasted this lines in my new text editor file then i saved it and exit
   `<?php
phpinfo();`

c. I accessed this page in my web browser
   `http://`3.236.166.163`/info.php`
   ![php browser](\images\browser2.PNG)

d. I tried removing the file i created but it didn't work out. I tried troubleshooting but i still couldn't remove it.
   `sudo rm /var/www/your_domain/info.php`


## Step 6
a. I connected to mysql console
   `sudo mysql`
  ![mysql console](\images\image18.PNG)


b. I created a new database
   `mysql> CREATE DATABASE `graceful_database`;`
   ![graceful database](\images\image19.PNG)


c. I created a new user
   `mysql>  CREATE USER 'graceful_user'@'%' IDENTIFIED WITH mysql_native_password BY 'password';`
   ![graceful user](\images\image20.PNG)


d. I gave the user permission over the database
   `mysql> GRANT ALL ON graceful_database.* TO 'graceful_user'@'%';`
   ![grant permission](\images\image21.PNG)

e. I exit the mysql shell
   `mysql> exit`
  ![exit mysql](\images\image22.PNG)

f. Then, I tested if the new user have proper permission
   `mysql -u graceful_user -p`
   ![test user](\images\image23.PNG)

g. I confirmed my access to the database
    `mysql> SHOW DATABASES;`
    ![show database](\images\image24.PNG)

h. Then I created a test-table named todo_list

    `CREATE TABLE example_database.todo_list (
mysql>     item_id INT AUTO_INCREMENT,
mysql>     content VARCHAR(255),
mysql>     PRIMARY KEY(item_id)
mysql> );`
    ![test table](\images\image25.PNG)

i. I inserted a row of content in the test table
   `mysql> INSERT INTO graceful_database.todo_list (content) VALUES ("My first important item");`
   ![insert](\images\image26.PNG)

j. I confirmed that the data was successfully saved
    `mysql>  SELECT * FROM graceful_database.todo_list;`
    ![confirm data](\images\image26.PNG)

k. I exit the mysql console
    `mysql> exit`
    ![exit](\images\image27.PNG)

l. I created a php script that will connect to mysql
    `nano /var/www/projectLEMP/todo_list.php`
     ![php script](\images\image28.PNG)

m. I accessed the page in my web browser
   `http://<3.236.166.163>/todo_list.php`
   ![web browser](\images\browser3.PNG)










   




  





   



    

