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

#finally run the application
CMD ["node", "server.js"]