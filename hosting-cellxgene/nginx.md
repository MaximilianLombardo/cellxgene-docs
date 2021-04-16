# NginX

used nginx as reverse proxy in front of the cellxgene browsers.  
For a single browser, the nginx config looks like the example config shown below.

\# Default route to login  
server {  
    listen 443 ssl;  
    server\_name YOURHOSTNAME;  
  
    \# SSL  
    ssl\_certificate /etc/nginx/conf.d/domain.crt;  
    ssl\_certificate\_key /etc/nginx/conf.d/domain.key;  
  
    location /cellxgene\_example {  
        proxy\_set\_header Accept-Encoding "";  
        proxy\_pass                            [http://localhost:5007/](http://localhost:5007/);  
        proxy\_set\_header Host                 $http\_host;  
        proxy\_set\_header X-Real-IP            $remote\_addr;  
        proxy\_set\_header X-Forwarded-For      $proxy\_add\_x\_forwarded\_for;  
        proxy\_set\_header X-Forwarded-Proto    $scheme;  
        \# replacements  
        sub\_filter 'href="static' 'href="cellxgene\_example/static';  
        sub\_filter 'src="static' 'src="cellxgene\_example/static';  
        sub\_filter\_types \*;  
        sub\_filter\_once off;  
        \# To add basic authentication to v2 use auth\_basic setting.  
        auth\_basic "Registry realm";  
        auth\_basic\_user\_file /etc/nginx/conf.d/nginx.htpasswd;  
        client\_max\_body\_size 50M;  
    }  
     
}  
  
server {  
    listen 80 default\_server;  
  
    server\_name \_;  
  
    return 301 [https://$host$request\_uri](https://%24host%24request_uri/);  
}

  
One would start the browser using port 5007 and forward request from [https://YOURHOSTNAME/cellxgene\_example](https://yourhostname/cellxgene_example) to the cgx browser \([http://localhost:5007](http://localhost:5007/)\).  
What is also added is basic\_auth that adds a login request with a username and password.  The nginx.htpasswd file is generated using htpasswd.  
If you want to add additional browsers, this is done by just adding additional location stanzas and running the cxg on a different port.  
The additional location stanzas just need to be adapted accordingly \(proxy\_pass and sub\_filter lines\).  


