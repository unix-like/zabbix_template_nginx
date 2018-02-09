# zabbix_template_nginx

| item                                 | trigger                    |
| :----------------------------------: | :------------------------: |
| Accepts Connections per sec          | Nginx Service DOWN         |
| Handle Connections per sec           | All Worker DOWN            |
| Requests per sec                     | Nginx Worker become ZOMBIE |
| Nginx is running                     |                            |
| Reading Count                        |                            |
| keep-alive Count                     |                            |
| Writing Count                        |                            |
| Active Connections                   |                            |
| Number of Nginx Work Process         |                            |
| Number of Nginx Zombie Worker        |                            |
| Use Memory of Nginx                  |                            |
| Use Memory of Nginx Master Process   |                            |
| Use Memory of Nginx Worker Processes |                            |



适用于zabbix3.4及以上版本,此监控项目监控数据的采集实现并行收集,共包含3个文件:

1. userparameter_nginx.conf
2. nginx.xml
3. nginx_status.conf

其中`userparameter_nginx.conf`,`nginx_status.conf`需要分发到各个nginx服务器上，`nginx.xml`作为模版文件导入zabbix中。

在导入模板之后需要修改三个“宏”的值:

1. {$NGINX\_STUB\_PORT}
2. {$NGINX\_STUB\_SERVER}
3. {$NGINX_USER}

为对应的nginx状态监听端口和地址，以及nginx运行账户。
