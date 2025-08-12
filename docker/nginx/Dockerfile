FROM nginxinc/nginx-unprivileged:1.29-alpine-perl

#RUN apk update && apk upgrade
#
## Create a new user and group
#RUN addgroup -S nginx_group && adduser -S nginx_user -G nginx_group

COPY default.conf /etc/nginx/conf.d/default.conf
COPY --chown=nginx:nginx --chmod=0644 ./certs/cert.pem /etc/nginx/certs/cert.pem
COPY --chown=nginx:nginx --chmod=0600  ./certs/key.pem /etc/nginx/certs/key.pem
#RUN #chmod 644 /etc/nginx/certs/cert.pem && chmod 600 /etc/nginx/certs/key.pem
## Set proper ownership and permissions
#RUN chown -R nginx_user:nginx_group /var/cache/nginx && \
#    chown -R nginx_user:nginx_group /var/log/nginx && \
#    chown -R nginx_user:nginx_group /etc/nginx/conf.d && \
#    chown nginx_user:nginx_group /etc/nginx/nginx.conf && \
#    chmod -R 660 /etc/nginx/conf.d && \
#    chmod 644 /etc/nginx/nginx.conf && \
#    touch /var/run/nginx.pid && \
#    chown -R nginx_user:nginx_group /var/run/nginx.pid
#
## Switch to non-root user
#USER nginx_user
#
## Expose port
#EXPOSE 8080

# Start Nginx
CMD ["nginx", "-g", "daemon off;"]