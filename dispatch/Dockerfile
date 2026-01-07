FROM golang
WORKDIR /opt/server
COPY go.mod .
EXPOSE 8080
RUN mod init dispatch
RUN go get
RUN go build dispatch

CMD ["./dispatch"]