FROM phusion/baseimage:0.9.13

# Set environment
ENV HOME /root

# baseimage-dockers's init system
CMD ["/sbin/my_init"]

# Install Nginx.
RUN \
  add-apt-repository -y ppa:nginx/stable && \
  apt-get update && \
  apt-get install -y nginx && \
  rm -rf /var/lib/apt/lists/* && \
  echo "\ndaemon off;" >> /etc/nginx/nginx.conf && \
  chown -R www-data:www-data /var/lib/nginx

# Define mountable directories.
VOLUME ["/etc/nginx/sites-enabled", "/etc/nginx/certs", "/etc/nginx/conf.d", "/var/log/nginx", "/data"]

# Set up runit entry
RUN mkdir /etc/service/nginx
ADD nginx.sh /etc/service/nginx/run

# Expose ports.
EXPOSE 80
EXPOSE 443
