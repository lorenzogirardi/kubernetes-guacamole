# guacamole kubernetes

Here we are , another apache guacamole implementation in kubernetes

This service is designed to avoid the usage of mysql and create a standalone project  

The main idea is to use the **user-mapping.xml** as a config map

For production environment i suggest to add the ldap auth (ad.openldap,freeipa),  
mysql database should be managed with a dedicated instances and mantained in case of "exit"

## what is a bastion host
On the Internet, a bastion host is the only host computer that a company allows to be addressed   
directly from the public network and that is designed to screen the rest of its network from security exposure.

## how this tool can be used   
The tool is designed to be used when you have some dedicated service in production and you have to keep   
the control of access and account used , guacamole has the ability to manage the most used platforms (windows and linux)  
as host in backend to be reached from developers ... contractors ...   

## why in kubernetes 
Since the auth method could scale by configmap or ldap or mysql , is designed to scale  
we have also the benefits to have a low footprint compared to a traditional vm.  



## config to change 
Before deploy you need to specify the following parameters in guacamole folder 

- YOUR_DOMAIN to reflect your domain url in 03-guacamole-ing.yaml
- user YOUR_USERNAME / YOUR_MD5_PWD and hosts xml configuration in 04-guacamole-cfm.yaml following https://guacamole.apache.org/doc/gug/configuring-guacamole.html#user-mapping

screenshots

![windows](https://res.cloudinary.com/ethzero/image/upload/v1580850552/misc/guacamole-win.png)  
![linux](https://res.cloudinary.com/ethzero/image/upload/v1580850552/misc/guacamole-linux.png)  



## deploy  

> kubectl apply -f guacd  

> kubectl apply -f guacamole



You can secure the connection with kube-lego and use cillium to add network rules 
