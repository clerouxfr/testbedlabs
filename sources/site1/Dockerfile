FROM nginx
LABEL maintainer='eazytraining'
RUN apt-get update
RUN DEBIAN_FRONTEND=noninteractive apt-get install git -y
RUN rm -Rf /usr/share/nginx/html/*
RUN git clone https://github.com/clerouxfr/static-website-example.git /usr/share/nginx/html/ &&  \
    apt remove git -y
EXPOSE 80
ENTRYPOINT ["/usr/sbin/nginx", "-g", "daemon off;"]
