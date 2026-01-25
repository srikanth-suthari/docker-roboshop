#since it is a nodejs based application, we are taking node:20 docker image in this dockerfile
##This is the offcial docker image from node.js
FROM node:20

# Setting working directory for our application and its code
WORKDIR /opt/server

# Copying all the dependencies and libraries which are required to the application package.json is consisting of deps
COPY package.json .

# copying all the applicaion code to the workdir
COPY *.js .

# Exposing our application
EXPOSE 8080

# Installing all the required dependencies from the package.json using the its package manager
# npm is the package manager for the node.js
RUN npm install

# Setting environment variables for our application to communicate with other applications
ENV REDIS_HOST="redis" \
    CATALOGUE_HOST="catalogue" \
    CATALOGUE_PORT="8080"

# Connect or build the communication with other applications as needed
#
# Finally running the application using its commands in cmd field
# here we are running and starting our application with the runtime
CMD ["node", "server.js"]

