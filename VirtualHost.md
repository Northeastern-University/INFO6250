
```sudo mkdir -p /var/www/info6250.com/```

```sudo mkdir -p /var/www/m.info6250.com/```

```sudo chown -R $USER:$USER /var/www/info6250.com/```

```sudo chown -R $USER:$USER /var/www/m.info6250.com/```

```sudo chmod -R 755 /var/www/```
###deploy the application code and config to the new staging area
```cp html/m.index.html /var/www/m.info6250.com/```

```cp html/index.html /var/www/info6250.com/```

```sudo cp /etc/apache2/sites-available/000-default.conf /etc/apache2/sites-available/info6250.com.conf```

```sudo cp /etc/apache2/sites-available/000-default.conf /etc/apache2/sites-available/m.info6250.com.conf```

Modify info6250.com.conf
```
	ServerName info6250.com
        ServerAdmin admin@info6250.com
        DocumentRoot /var/www/info6250.com/
```
Modify m.info6250.com.conf
```
	ServerName m.info6250.com
        ServerAdmin admin@m.info6250.com
        DocumentRoot /var/www/m.info6250.com/
```
```sudo a2ensite info6250.com.conf```

```sudo a2ensite m.info6250.com.conf```

```sudo service apache2 restart```

####On the client side (mac, linux) configure the hostname in case you don’t have a real domain name e.g. info6250.com or m.info6250.com 
Configure /etc/hosts
40.124.12.183 m.info6250.com

40.124.12.183 info6250.com

Now simply browse to info6250.com and m.info6250.com and see if you got the results you wished for. 
