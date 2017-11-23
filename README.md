# Nginx-Varnish-cPanel

And why 3 webservers and not 2? 
- Because Varnish doesn't support SSL. SO, Well leave the Apache as the backend because cPanel will create all vHost configs for apache and we will setup Varnish as mid web server to cache website contents, and we will use nginx as primary webserver which supports both ssl and non ssl. Nginx will not be used just for Primary server or ssl, But will also be used for Security reasons and ModSecurity will be used. Because we can't leave Modsecurity ON when you have this configuration. example if modsecurity in cPanel will block a page you will not see the error but varnish will response with a simple page "503 Backend failed".

# TO DO.

 1 . Compile Nginx From Source.
 
 2 . Use Varnish For Cache.
 
 3 . Use Nginx As Primary Server to forward requests to varnish and varnish to apache.
 
 4 . ADD ModSecurity Rules To Nginx So In Case Of Errors Users Don't Get "[503] Backend Failed!" because we're using modsec in cPanel.
 
 5 . Re'build Varnish `default.vcl` because as of now is outdated for varnish 5.2
 
 6 . Build a simple panel to manage this.


# Reqs.

Tests are done on CentOS 7.4 And so you should have CentOS 7.4 to use this or if you have knowledge about those you can use in different version but i don't suggest it.

About resources. 
This needs +5GB RAM. And a good CPU. (Disk SSD, But isn't problem even if you're on HDD) 

# Try (TESTING ONLY)

First install manually latest `libmaxminddb` and `libmaxminddb-devel` or installation will fail.
then

1. `cd ~; wget https://raw.githubusercontent.com/DopeCloud/nginx-varnish-cpanel/master/install`

2. `chmod +x ./install; ./install`

3. `nginx -t`

Commands

`service varnish start/stop/restart etc`

`service nginx start/stop/restart etc`

As this is just testing because there is no full setup yet and there is no gui but just cli so as of now i've create a beta installation script and i'm currently working with default vhosts config -> `https://github.com/DopeCloud/nginx-varnish-cpanel/blob/master/nginx/live/default`

*Feel free to suggest something or submit a pull req*


# How to remove this?!
Here is no "autoremove" script as of now. so you can shutdown nginx/varnish and change apache non-ssl/ssl ports back to its default. as of varnish you can remove it by just "yum remove varnish" but nginx is compiled from source so it will be a problem to remove it if you don't have too much knowledge. if you have then check out 'install' file to see all dirs which are in use for nginx and remove them
