FROM maven
WORKDIR /opt/server
COPY *.java .
EXPOSE 8080
RUN mvn clean package
RUN mv src/target/com.shipping.jar shipping.jar
CMD ["java", "-j", "shipping.jar"]
