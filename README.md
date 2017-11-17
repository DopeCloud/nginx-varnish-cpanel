# Nginx-Varnish-cPanel

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
