# Install MYSQL server and MYSQL Workbench in UBUNTU.
 
### UBUNTU Operating System - Canonical Ltd., Ubuntu community

 - Installtion of the server
   - Use the following command to install the MYSQL Server:
     - **Download:** **`sudo apt-get install mysql-server`**
     - **Secure Installation:** **`sudo mysql_secure_installation`**
     
 - Login to MYSQL Server
   - Use the following command to install the MYSQL Server:
     - **Login:** **`sudo mysql -u root -p`**
     
 - Check the installation by fetching the databases
   - Use the following command to install the MYSQL Server:
      - **Showing All Databases:** **`show databases;`**
 
 - Start/Stop the MYSQL Server
   - Start: **`sudo /etc/init.d/mysql start`**
   - Stop: **`./mysqladmin -u root -p shutdown`**
   
 - Installation of the MYSQL Workbench:
   - Download the Installation Files from the [Official URL](https://dev.mysql.com/downloads/workbench/)
   - Select the respective OS before downloading and install it.
   
 - **NOTE:** The default port of the server is `3306`
 
 - Error while connecting to local database server: **"Cannot Connect to Database Server"**
   - Follow the step as given below:
     - Exit the server connection: **`exit`**
     - Login: **`sudo mysql -u root -p`**
     - Select the database: **`use mysql;`**
     - Set plugin: **`UPDATE user set plugin='mysql_native_password' WHERE user='root';`**
     - Set Authentication string for mysql user: **`UPDATE mysql.user set authentication_string=PASSWORD(' <your_password> ') where       user='root';`**
     - Flushing Priviledges: **`FLUSH PRIVILEGES;`**
     - Quit: **`quit`**
     
 - Connect to database installed on the remote server using Ubuntu Terminal and Mysql Workbench:
   - **NOTE:** It is important to note that the default user (root) is not directly accessible remotely.
   - So create a new/ custom user and grant the privileges accordingly uisng the following commands:
     - **`CREATE USER 'username'@'localhost' IDENTIFIED BY 'password';`**
     - **`GRANT ALL PRIVILEGES ON *.* TO 'username'@'localhost' WITH GRANT OPTION;`**
     - **`CREATE USER 'username'@'%' IDENTIFIED BY 'password';`**
     - **`GRANT ALL PRIVILEGES ON *.* TO 'username'@'%' WITH GRANT OPTION;`**
     - **`FLUSH PRIVILEGES;`**
   - Change the line: **bind-address 127.0.0.1** to **bind-address 0.0.0.0** so that the DB is accessible from all the IP addresses in the file `/etc/mysql/mysql.conf.d/mysqld.cnf.`
   - Connect to the mysql server using the following command:
     - **`mysql -u <username> -p<password> -h <remote server ip or name> -P <port> -D <DB name>`**
     - **`NOTE:`** There is no space after -p.
 - Connect again and you are ready to go!!
