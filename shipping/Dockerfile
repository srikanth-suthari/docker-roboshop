#Here we are using maven to build our application as our application is written in java
FROM maven:3.9.11

#This creates a directory for the application
WORKDIR /opt/server

#This will copy the pom.xml file to the workdir which has all the dependencies and libraries
COPY pom.xml .

#Here we are copying the src directory into the container as /src directory with all the files and folders within it
COPY src ./src

#Exposing on the port 8080
EXPOSE 8080

#here we install all the dependencies from maven repository and build it into a .jar file as an executable using this command
RUN mvn clean package

#Here we are changing the name of our artifact from com.shpping.jar to shipping.jar
RUN mv src/target/com.shipping.jar shipping.jar

#At final we are running our application or .jar file using java runtime in the conatiner
CMD ["java", "-j", "shipping.jar"]
