FROM nginx:1.29.4-alpine

RUN rm /etc/nginx/nginx.conf /etc/nginx/conf.d/default.conf

RUN addgroup -S roboshop && adduser -S roboshop -G roboshop

USER roboshop

RUN mkdir -p /var/cache/nginx/client_temp && \
        mkdir -p /var/cache/nginx/proxy_temp && \
        mkdir -p /var/cache/nginx/fastcgi_temp && \
        mkdir -p /var/cache/nginx/uwsgi_temp && \
        mkdir -p /var/cache/nginx/scgi_temp && \
        chown -R nginx:nginx /var/cache/nginx && \
        chown -R nginx:nginx /etc/nginx/ && \
        chmod -R 755 /etc/nginx/ && \
        chown -R nginx:nginx /var/log/nginx

RUN mkdir -p /etc/nginx/ssl/ && \
    chown -R nginx:nginx /etc/nginx/ssl/ && \
    chmod -R 755 /etc/nginx/ssl/

RUN touch /var/run/nginx.pid && \
        chown -R nginx:nginx /var/run/nginx.pid /run/nginx.pid
COPY nginx.conf /etc/nginx/nginx.conf
COPY static /usr/share/nginx/html/
USER nginx
CMD ["nginx", "-g", "daemon off;"]
# FROM nginx
# RUN rm -rf /usr/share/nginx/html/index.html
# RUN rm -rf /etc/nginx/nginx.conf
# RUN rm -rf /etc/nginx/conf.d/default.conf
# COPY nginx.conf /etc/nginx/nginx.conf
# COPY static /usr/share/nginx/html/

# #this is frontend

# FROM nginx

# # Removing the default index.html from /nginx/html directory
# RUN rm -rf /usr/share/nginx/html/index.html

# # Removing the default nginx.conf
# RUN rm -rf /etc/nginx/nginx.conf

# #Removing the default.conf from the /etc/nginx/conf.d/ directory
# RUN rm -rf /etc/nginx/conf.d/default.conf

# # Copying our customized nginx.conf to the default directory based on our requirements
# COPY nginx.conf /etc/nginx/nginx.conf

# # Copying all the static files, templates to the /nginx/html/ directory
# # and it consists of all the frontend code, static images, templates and css related files etc
# COPY static /usr/share/nginx/html/

# # finally running the nginx serivce
# CMD ["nginx", "-g", "daemon off;"]
