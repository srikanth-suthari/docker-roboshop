FROM golang
WORKDIR /opt/server
COPY main.go .
EXPOSE 8080
RUN mod init dispatch
RUN go get
RUN go build dispatch

CMD ["./dispatch"]