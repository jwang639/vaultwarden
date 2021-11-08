# VaultWarden with MySQL<a name="overview"></a>
For testing or studying, please go to the "Deploy VaultWarden with local MySQL Container" part.  
For production, please go to the "Deployment with External MySQL Services" part.<br></br>
To know more about VaultWarden please go to: https://github.com/dani-garcia/vaultwarden/wiki/Using-the-MariaDB-(MySQL)-Backend

To enable the admin page, you need to set an authentication token. This token can be anything, but it's recommended to use a long, randomly generated string of characters, for example running openssl rand -base64 48. Keep this token secret, this is the password to access the admin area of your server!

To set the token, use the ADMIN_TOKEN variable
# Table of contents
1. [Overview](#overview)
2. [Deployment with Local MySQL Container](#DeploymentwithLocalMySQLContainer)
    * [Start Services](#StartServicesLocal)
    * [Stop Services](#StopServicesLocal)
    * [Check Logs](#CheckLogsLocal)
    * [Check Container State](#CheckContainerStateLocal)
3. [Deployment with Extral MySQL Container](#DeploymentwithExternalMySQLContainer)
    * [Start Services](#StartServices)
    * [Stop Services](#StopServices)
    * [Check Logs](#CheckLogs)
    * [Check Container State](#CheckContainerState)
<br> </br>

# Deploy VaultWarden with local MySQL Container<a name="DeploymentwithLocalMySQLContainer"></a>
RECOMMEDED FOR LOCALHOST SETUP. BEST SUITED FOR DEVELOPMENT & TESTING.<br> </br>
These sets of instructions are used for running **TWO** containers.

* 1st Container - MySQL(mariadb) 
* 2nd Container - vaultwarden server.
* To change the default mariadb credentials, modify the `.env` file.  
(Reminder: Please ensure you are using `docker-compose.yml` and `.env` files in deployingment with local MySQL)

### **Start Services** <a name="StartServicesLocal"></a>
`docker-compose up -d --build` <br>
(Note: `-d` flag will run the services in background)
### **Stop Services** <a name="StopServicesLocal"></a>
`docker-compose down` <br>
### **Check logs** <a name="CheckLogsLocal"></a>
`docker-compose -f docker-compose.yml logs -f vaultwarden` <br>

### **Check container state** <a name="CheckContainerStateLocal"></a>
`docker-compose -f docker-compose.yml ps` <br>

# Deployment with External MySQL Services <a name="DeploymentwithExternalMySQLContainer"></a>
RECOMMENDED FOR PRODUCTION SETUP IN A CLOUD ENVIRONMENT.

If you have MySQL deployed in cloud or on some remote instance, use this option with `docker-compose.prod.yml` and `.env.prod`  

### **Connection String Syntax:**
`DATABASE_URL=mysql://[[user]:[password]@]host[:port][/database]`
  
  The below instructions only spins up a single container.   

* Single Container - vaultwarden only
### **Start Services** <a name="StartServices"></a>
`docker-compose -f docker-compose.prod.yml up -d --build` <br>
(Note: `-d` flag will run the services in background)
### **Stop Services** <a name="StopServices"></a>
`docker-compose -f docker-compose.prod.yml down` <br>
### **Check logs** <a name="CheckLogs"></a>
`docker-compose -f docker-compose.prod.yml logs -f vaultwarden` <br>

### **Check container state** <a name="CheckContainerState"></a>
`docker-compose -f docker-compose.prod.yml ps` <br>
