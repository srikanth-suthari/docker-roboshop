FROM golang
WORKDIR /opt/server
COPY main.go .
EXPOSE 8080
RUN go mod init dispatch
RUN go get
RUN go build dispatch

ENV AMPQ_HOST="rabbitmq" \
    AMPQ_USER="roboshop" \
    AMPQ_PASS="roboshop123"

CMD ["./dispatch"]