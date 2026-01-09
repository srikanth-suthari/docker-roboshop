FROM nginx

# Removing the default index.html from /nginx/html directory
RUN rm -rf /usr/share/nginx/html/index.html

# Removing the default nginx.conf
RUN rm -rf /etc/nginx/nginx.conf

#Removing the default.conf from the /etc/nginx/conf.d/ directory
RUN rm -rf /etc/nginx/conf.d/default.conf

# Copying our customized nginx.conf to the default directory based on our requirements
COPY nginx.conf /etc/nginx/nginx.conf

# Copying all the static files, templates to the /nginx/html/ directory
# and it consists of all the frontend code, static images, templates and css related files etc
COPY static /usr/share/nginx/html/