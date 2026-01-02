# Here we are taking official mysql image from the docker hub
FROM mysql:8.0

# Copying the necessary files like init script to the docker entrypoint at this location for initialising the mysql db
COPY db /docker-entrypoint-initdb.d

# Copying the custom script to the /usr/local/bin/ location for checking the root user and its password
COPY custom-script.sh /usr/local/bin/custom-script.sh

# Run the command to change the necessary permissions to/on the file to be able to executalbe
RUN chmod +x /usr/local/bin/custom-script.sh

# In this final step we are running the container and making it alive after docker initialises the docker container
ENTRYPOINT ["/usr/local/bin/custom-script.sh"]

# Entrypoint takes care to make the container alive after spinning up the database or the application like nginx, apache and ubuntu with sleep 1000 etc
