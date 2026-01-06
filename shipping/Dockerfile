#Here we are using maven to build our application as our application is written in java
FROM maven
WORKDIR /opt/server
COPY src .
EXPOSE 8080
RUN mvn clean package
RUN mv src/target/com.shipping.jar shipping.jar
CMD ["java", "-j", "shipping.jar"]
