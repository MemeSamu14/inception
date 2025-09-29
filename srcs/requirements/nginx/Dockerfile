FROM debian:bullseye

RUN  apt-get update \
     && apt-get install -y nginx openssl \
     && apt-get clean \
     && rm -rf /var/lib/apt/lists/*

COPY ./conf/nginx.conf /etc/nginx/conf.d/

RUN mkdir -p /etc/nginx/ssl

RUN openssl req -newkey rsa:2048 -x509 -sha256 -days 365 -nodes \
     -keyout /etc/nginx/ssl/file.key \
     -out /etc/nginx/ssl/file.crt \
     -subj "/C=IT/ST=Toscana/L=Firenze/O=42 Firenze/OU=IT/CN=login.42.fr/emailAddress=sfiorini@student.42firenze.it"

RUN mkdir -p /run/nginx

ENTRYPOINT ["nginx"]
CMD ["-g", "daemon off;"]