# guacamole kubernetes

Here we are , another apache guacamole implementation in kubernetes

This service is designed to avoid the usage of mysql and create a standalone project  

The main idea is to use the **user-mapping.xml** as a config map


Before deploy you need to specify the following parameters in guacamole folder 

- YOUR_DOMAIN to reflect your domain url in 03-guacamole-ing.yaml
- user and host xml configuration in 04-guacamole-cfm.yaml following https://guacamole.apache.org/doc/gug/configuring-guacamole.html#user-mapping


To deploy  

> kubectl apply -f guacd  

> kubectl apply -f guacamole



You can secure the connection with kube-lego and use cillium to add network rules 
