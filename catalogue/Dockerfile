#our application is in nodejs
FROM node:20

#setting workdir
WORKDIR /opt/server

#COPY dependencies and libraries of the application
COPY package.json .

#copy the application code to workdir
COPY *.js .

#exposing the application
EXPOSE 8080

#install the required dependencies
RUN npm install

# Setting Env to mongodb connection
ENV MONGO="true" \
    MONGO_URL="mongodb://mongodb:27017/catalogue"

#finally run the application
CMD ["node", "server.js"]