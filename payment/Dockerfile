# Here we are taking python3 based image as our base os
FROM python3.9
WORKDIR /opt/server
EXPOSE 8080
COPY payment.ini .
COPY *.js .
COPY requirements.txt .
RUN pip3 install -r requirements.txt
ENV CART_HOST="cart" \
    CART_PORT="8080" \
    USER_HOST="user" \
    USER_PORT="8080" \
    AMPQ_HOST="rabbitmq" \
    AMPQ_USER="roboshop" \
    AMPQ_PASS="roboshop123"
CMD ["uwsgi", "--ini", "payment.ini"]