# VaultWarden with MySQL

These sets of instructions are used for running **TWO** containers.

* 1st Container - MySQL(mariadb) 
* 2nd Container - vaultwarden server.
* To change the default mariadb credentials, modify the `.env` file.

# Deploy VaultWarden via docker-compose file 


### **Start Services** 
`docker-compose up -d` <br>
(Note: `-d` flag will run the services in background)
### **Stop Services** 
`docker-compose down` <br>

### **Reference** 
To know more about VaultWarden please go to:https://github.com/dani-garcia/vaultwarden/wiki/Using-the-MariaDB-(MySQL)-Backend
