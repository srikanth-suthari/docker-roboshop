# Here we are taking python3 based image as our base os
FROM python:3.9

# setting workdir
WORKDIR /opt/server

# exposing the application
EXPOSE 8080

# copying the required files and their dependency files
COPY payment.ini .
COPY *.js .
COPY requirements.txt .

# run and install dependencies
RUN pip3 install -r requirements.txt

# setting the env to the application
ENV CART_HOST="cart" \
    CART_PORT="8080" \
    USER_HOST="user" \
    USER_PORT="8080" \
    AMQP_HOST="rabbitmq" \
    AMQP_USER="roboshop" \
    AMQP_PASS="roboshop123"

# finally running the application with uwsgi
# uwsgi works as a webserver to the python runtime --> like nginx for other applications
CMD ["uwsgi", "--ini", "payment.ini"]