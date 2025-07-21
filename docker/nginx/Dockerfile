FROM nginx:1.29-alpine

# Create a new user and group
RUN addgroup -S nginx_group && adduser -S nginx_user -G nginx_group

# Set proper ownership and permissions
RUN chown -R nginx_user:nginx_group /var/cache/nginx && \
    chown -R nginx_user:nginx_group /var/log/nginx && \
    chown -R nginx_user:nginx_group /etc/nginx/conf.d && \
    chmod -R a-xw /etc/nginx/conf.d && \
    touch /var/run/nginx.pid && \
    chown -R nginx_user:nginx_group /var/run/nginx.pid

# Switch to non-root user
USER nginx_user

# Expose port
EXPOSE 8080

# Start Nginx
CMD ["nginx", "-g", "daemon off;"]