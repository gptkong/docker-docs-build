# Use nginx as the base image
FROM nginx:alpine

# Install git
RUN apk add --no-cache git

# Create a directory for the documentation
WORKDIR /usr/share/nginx/html

# Clone the repository and checkout gh-pages branch
RUN git clone https://github.com/immerjs/immer.git /tmp/immer && \
    cd /tmp/immer && \
    git checkout gh-pages && \
    cp -r ./* ./.??* /usr/share/nginx/html/ && \
    rm -rf /tmp/immer

# Create custom nginx configuration
RUN echo 'server { \
    listen 80; \
    server_name localhost; \
    root /usr/share/nginx/html; \
    index index.html; \
    location / { \
        try_files $uri $uri/ /index.html; \
    } \
    location /immer/ { \
        alias /usr/share/nginx/html/; \
        try_files $uri $uri/ /index.html; \
    } \
}' > /etc/nginx/conf.d/default.conf

# Expose port 80
EXPOSE 80

# Start Nginx
CMD ["nginx", "-g", "daemon off;"]
