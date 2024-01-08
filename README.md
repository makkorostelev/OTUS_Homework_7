# OTUS_Homework_7
 
Project creates one YC LB, 2 nginx proxy server, 2 nginx+php-fpm+wordpress backends, pxc cluster+proxysql(3 servers), OpenSearch cluster(3 servers) and OpenSearch Dashboard.\
### Project Scheme
![Project Scheme](https://github.com/makkorostelev/OTUS_Homework_7/blob/main/Screenshots/scheme.png)\


### Prerequisite

- **Ansible 2.9+**
- **Java 8**

To work with the project you need to write your data into variables.tf.\
![Variables](https://github.com/makkorostelev/OTUS_Homework_7/blob/main/Screenshots/variables.png)\
Then enter the commands:
`terraform init`\
`terraform apply`

After ~5 minutes project will be initialized and run:\
Below there is an example of successful set up:

```
Outputs:

admin_ip = "51.250.34.140"
backend_ips = [
  "10.5.0.6",
  "10.5.0.37",
]
database_ips = [
  "10.5.0.28",
  "10.5.0.30",
  "10.5.0.11",
]
lb_ip = "51.250.37.43"
nginx_ips = [
  "10.5.0.7",
  "10.5.0.8",
]
opensearch_dashboard_ip = "51.250.33.151"
opensearch_ips = [
  "10.5.0.3",
  "10.5.0.4",
  "10.5.0.27",
]

```

To log in to OpenSearch Dashboard go to http://opensearch_dashboard_ip:5601 and enter the following credentials:
Username: `admin`
Password: `Test@123`

On the Discover tab you can view syslog from all project servers
![Opensearch_discover](https://github.com/makkorostelev/OTUS_Homework_7/blob/main/Screenshots/opensearch_discover.png)

You can go to http://lb_ip and add your wordpress template to that installation :\
![Wordpress](https://github.com/makkorostelev/OTUS_Homework_7/blob/main/Screenshots/wordpress.png)
Even if one of nginx or pxc servers will be shutdown everything will work as it should
