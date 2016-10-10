####Redirect Users to Mobile or Normal Web Site Based on user-agent using mod_rewrite

##Refer to the virtual host set up of info6250.com and m.info6250.com.
```sudo a2enmod rewrite```

Add to /etc/apache2/sites-enabled/info6250.com.conf
```
	<Directory /var/www/info6250.com/public_html>
                AllowOverride All
        </Directory>
```
Add to /etc/apache2/sites-enabled/m.info6250.com.conf
```
        <Directory /var/www/m.info6250.com/public_html>
                AllowOverride All
        </Directory>
```
```
cat /var/www/info6250.com/public_html/.htaccess 
<IfModule mod_rewrite.c>
RewriteEngine On
RewriteCond %{HTTP_USER_AGENT} "android|blackberry|googlebot-mobile|iemobile|ipad|iphone|ipod|opera mobile|palmos|webos" [NC]
RewriteRule ^$ http://m.info6250.com/ [L,R=302]
</IfModule>

cat /var/www/m.info6250.com/public_html/.htaccess 
<IfModule mod_rewrite.c>
RewriteEngine On
RewriteCond %{HTTP_USER_AGENT} "!(android|blackberry|googlebot-mobile|iemobile|ipad|iphone|ipod|opera mobile|palmos|webos)" [NC]
RewriteRule ^$ http://info6250.com/ [L,R=302]
</IfModule>
```
