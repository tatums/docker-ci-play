FROM ubuntu
RUN apt-get update -qq && apt-get install -y build-essential libpq-dev
RUN apt-get install -y nginx

RUN echo "daemon off;" >> /etc/nginx/nginx.conf
RUN mkdir /etc/nginx/ssl
ADD default /etc/nginx/sites-available/default

EXPOSE 80
CMD ["nginx"]
