## Africa Systems
### Odoo instance deployment procedure

`docker` or `docker-compose`  are two great tools when it comes
to simplifying application deployment. Odoo is one of the
core system used at A.S. This document intend to describe
how to deploy an odoo instance using `docker-compose`

#### Steps

* Clone the code on your server
* Position your self on the branch corresponding to the odoo version you want to deploy
* Create the containers
* Update the configuration file accuratly, using the provided template in this repository

#### Nota Bene !!!

You can also update the `docker-compose.yml` file for stuff like:
* updating odoo ports
* updating database ports
* updating volumes paths

##### Have FUN !!!