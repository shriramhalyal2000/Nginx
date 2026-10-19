# Nginx poc 
- as reverse proxy, webserer, ssl and loadbalncer
- as proxy is used to mask bakend serves and those servers arealso loadbalanced to protect them from overloading.

- upstream is a block used to loadbalance the servers and use them to add target servers to be loadbalanced.
- the block is by default round robin,
  - but if used lest_conn;, ip_host; algorithm to loadbalance.
- the ssl_certificate directive can be used to set certificate file location and ssl_certificate_key directive to set location of certificate key files.
- for this the server has to listen for 443 port for https:// connection.
- and you can also add another server block to re-direct the http:// request to https:// 

*.config in ./sites-available/domain_name/file and put the same file in ./sites-enabled/ to activate the configuration.