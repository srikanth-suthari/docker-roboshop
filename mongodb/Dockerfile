# Using mongodb official image in our project as our document or nosql database
FROM mongo:7.0

# copy the required code or collection code to the docker-entrypoint-initdb.d location
# after copying docker will automatically create all the required schemas as mentioned in the collection code
COPY *.js /docker-entrypoint-initdb.d

#"/docker-entrypoint-initdb.d" is the default location for storing or initialsing the database in a docker container
