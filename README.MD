## monadeware
### Odoo instance deployment procedure

`docker` and `docker-compose`  are two great tools for simplifying application deployment. This document intends to describe
how to deploy an odoo instance using `docker-compose`.

#### Steps

* Clone the code on your server
* Edit line 4 in ```docker-compose.yml``` to precise the odoo version you want to deploy

    ```image: odoo:<my_preferred_version>```
    
* update application port
      use nano editor to edit public port in docker-compose.yml line 9
      
      ```- "0.0.0.0:<desire_port>:8069"```
      
* Create the containers

    ```docker-compose up -d```
    
* Update the configuration file accurately, using the provided template in this repository
    
    ```under ./config/odoo.conf ```

    ``` and add your modules under ./addons```

the above files (./config and ./addons) are automatically added to your current directory after you run ```docker-compose up -d``` command


* To install a new Python package in the container, just use the following:

``` docker exec -it <container_id> pip3 install <package_name>```

#### Accessing odoo shell

``` docker exec -it <container_id> <db_user> shell -d <db_name> --db_host postgres --db_password <db_password> ```

db_user, db_password can be found in the .env file.

#### Uninstalling module from shell

``` self.env['ir.module.module'].search([('name', '=', '<module_name>')]).button_immediate_uninstall() ```

#### Nota Bene !!!

You can also update the `docker-compose.yml` file for stuff like:
* updating odoo ports
* updating database ports
* updating volumes paths

##### Have FUN !!!
