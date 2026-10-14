# Nginx

- A high performance reverse-proxy, webserver for static http content, load-balancer and http-caching

- Nignx primerily used as a ewb server and reverse proxy in most cases to serve http content to incoming user requests.

- Nginx can be configuired with 3 main directory namely:
  - /var/www/html to serve the content, directory created by nginx to recognize content placed here directed by the *.conf files
  - *.conf files are served in primarily two places:
    - /etc/nginx/sites-available: for storing n-number of site configuration.
    - and a sister file of same name and content at /etc/nginx/sites-enabled: at here nginx recognizes the files config is ready to be served with the target content location at said /var/www/html dir.

- A sample Server block config:
  - server{
    listern 80;
    server_name localhost;

    root /var/www/html;
    index index.html;

    location /{
        try_files $uri $uri/ = 404;
    }
  }


  breakdown:

  - listen 80; listen at HTTP port 80;
  - server_name localhost - Domain or IP to repond to.
  - root path where NGINX looks for files/content to serve.
  - index default file to server (usually index.html)
  - location / URL path handling