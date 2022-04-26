```shell
sudo docker-compose up
sudo docker-compose up -d

http://49.232.6.131:8074/
cn=admin,dc=7otech,dc=com
admin

sudo yum install openldap
sudo yum install openldap-servers

sudo docker run -p 389:389 -p 636:636 --name my-openldap-container --detach osixia/openldap:1.5.0
sudo docker run -p 389:389 -p 636:636 \
	--env LDAP_ORGANISATION="7otech" \
	--env LDAP_DOMAIN="7otech.com" \
	--env LDAP_ADMIN_PASSWORD="admin" \
	--detach osixia/openldap:1.5.0
sudo docker exec my-openldap-container ldapsearch -x -H ldap://localhost -b dc=7otech.com,dc=org -D "cn=admin,dc=7otech.com,dc=org" -w admin

sudo docker run -p 8074:443 \
        --env PHPLDAPADMIN_LDAP_HOSTS=172.21.16.11 \
        --detach osixia/phpldapadmin:0.9.0

https://49.232.6.131:8074/
cn=admin,dc=7otech,dc=com
admin

ldap://172.21.16.11:389
dc=7otech,dc=com

ou=tech,dc=7otech,dc=com
ou=People,dc=7otech,dc=com

cn=test,ou=People,dc=7otech,dc=com

https://zhuanlan.zhihu.com/p/445690193
https://www.cnblogs.com/dufeixiang/p/11624210.html
https://zhuanlan.zhihu.com/p/445692541
```

```
ldap 管理

DC：domain component一般为公司名，例如：dc=163,dc=com
OU：organization unit为组织单元，最多可以有四级，每级最长32个字符，可以为中文
CN：common name为用户名或者服务器名，最长可以到80个字符，可以为中文
DN：distinguished name为一条LDAP记录项的名字，有唯一性，例如：dc:"cn=admin,ou=developer,dc=163,dc=com"
```