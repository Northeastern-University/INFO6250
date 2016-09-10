# INFO6250
INFO6250 Course Repo

We are going to use this repo for AngularJS practice. We will need a web server that loaded with php and js. 


For those who uses Mac, please follow the instructions below:

## Setup Apache + PHP
1. Update your Mac to latest OS X Yosemite.
2. First, open Terminal and switch to root to avoid permission issues while running these commands.
```sudo su -```
3. Enable Apache on Mac OS X
```apachectl start```
4. Verify It works! by accessing ```http://localhost```
5. Enable PHP for Apache
```vi /etc/apache2/httpd.conf```
Uncomment the following line (remove #):

```LoadModule php5_module libexec/apache2/libphp5.so```

6. Restart Apache:
```apachectl restart```

7. Deploy your static app to ```/Library/WebServer/Documents/```
8. Deploy the hello.html to the folder at #7
