# Here we are using official golang image, because our application is written in go lang
FROM golang

# Setting up the workdir
WORKDIR /opt/server

#Copying required files
COPY main.go .

#Exposing the application
EXPOSE 8080

#Running commands and installing required dependencies for the application
RUN go mod init dispatch
RUN go get
RUN go build dispatch

#Setting up the env to communicate with other services
ENV AMPQ_HOST="rabbitmq" \
    AMPQ_USER="roboshop" \
    AMPQ_PASS="roboshop123"

#Finally running the binary/executable of the compiled go application.
CMD ["./dispatch"]