FROM debian:jessie

WORKDIR /tmp/nginx

RUN apt-get update \
    && apt-get install -y nginx openssl \
    && openssl req \
      -x509 \
      -subj "/C=US/ST=TX/L=Austin/O=Home/CN=nodeops.com" \
      -nodes \
      -days 365 \
      -newkey rsa:2048 \
      -keyout /etc/ssl/private/nginx-selfsigned.key \
      -out /etc/ssl/certs/nginx-selfsigned.crt

COPY nginx.conf /etc/nginx/nginx.conf

CMD ["nginx", "-g", "daemon off;"]
