FROM maven
WORKDIR /opt/server
COPY *.java .
EXPOSE 8080
RUN mvn clean package
CMD ["java", "-j", "shipping.jar"]
