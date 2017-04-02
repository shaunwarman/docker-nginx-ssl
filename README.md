# docker-nginx-ssl

### Overview
A dockerized setup for nginx handling SSL termination and forwarding traffic to node application. 
Docker handles the installation of openSSL, nginx and certificate creation and installation.

### Prerequisites
- [Docker](https://docs.docker.com/engine/installation/)
- [Docker compose](https://docs.docker.com/compose/install/)

### Usage
```
# clone repository
git clone https://github.com/shaunwarman/docker-nginx-ssl.git

# change directory
cd docker-nginx-ssl

# run docker compose setup
docker-compose up

# test secure request
curl -v https://localhost:443
```

### Output
```
$ curl -v https://127.0.0.1:443

...

* SSL connection using TLSv1.2 / ECDHE-RSA-AES256-GCM-SHA384
* ALPN, server did not agree to a protocol
* Server certificate:
*  subject: C=US; ST=TX; L=Austin; O=Home; CN=nodeops.com
*  start date: Apr  2 02:34:01 2017 GMT
*  expire date: Apr  2 02:34:01 2018 GMT
*  issuer: C=US; ST=TX; L=Austin; O=Home; CN=nodeops.com
*  SSL certificate verify result: self signed certificate (18), continuing anyway.
> GET / HTTP/1.1
> Host: 127.0.0.1
> User-Agent: curl/7.52.1
> Accept: */*
>
< HTTP/1.1 200 OK
< Server: nginx/1.6.2
< Date: Sun, 02 Apr 2017 02:34:18 GMT
< Content-Type: text/plain
< Content-Length: 2
< Connection: keep-alive
< Strict-Transport-Security: max-age=31536000

...
```
