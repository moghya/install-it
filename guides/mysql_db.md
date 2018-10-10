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
     
 - Connect again and you are ready to go!!
