# we are using node as our base image as our application is written in nodejs
FROM node:20

# setting the working directory inside the container
WORKDIR /opt/server

# copying the dependencies file and application code to the working directory
COPY package.json .

# copying all the application code to the working directory
COPY *.js .

# exposing the application on port 8080
EXPOSE 8080

# installing all the dependencies from package.json
RUN npm install

# installing redis client as our application is communicating with redis cache
ENV MONGO="true" \
    REDIS_URL="redis://redis:6379" \
    MONGO_URL="mongodb://mongodb:27017/users"

# finally running the application using node runtime
CMD ["node", "server.js"]
