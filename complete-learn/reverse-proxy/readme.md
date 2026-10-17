# Nginx as R-proxy;

- Nginx can serve content without actually exposing the backend or private ip+port link/dns to incoming client interwork requests.
- it can serve those requests whislt protecting the main backend/andy server that are ment to be private.
-This is achived with adding reverse proxy settings in /etc/sites-available/*.conf files.
  - within server block of location /{}.
  - adding proxy_pass to listen at the dns, like any localhost or prefered DNS.
  - the adding proxy_pass_header it forwards request to the DNS or server to which its proxing for.
  - proxy_set_header  X-Real-IP $remote_addrit preserves the original ip and host of the requester to forward to after it recives the information from backend server.
  - in the server block its learredy using listen : for to listen at requred port preferbly port 80;
  - and server_name is at localhost in server block.
- and ofcourse the files have to be mirred , of whatever the files it having to be enabled have to be available in .
 - only put actively serving config files in ../sites-enlabled, 