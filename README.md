# How to start MongoDB in Docker

docker run -d -p 27017:27017 --name=demo mongo:latest

# How to start MonoDB in Docker with specific username and password?

docker run -d -p 27017:27017 -e MONGO_INITDB_ROOT_USERNAME=rootUser -e MONGO_INITDB_ROOT_PASSWORD=rootPassword --name=demo mongo:latest --auth

# Setting in application.properties (the most important one)
spring.data.mongodb.uri=mongodb://rootUser:rootPassword@localhost:27017/oc.patient?authSource=admin

?authSource=admin: This part is crucial for authentication. It specifies the database where your credentials (rootUser and rootPassword) are stored. In this case, it's set to admin, a common practice.


# The client tool "MongoDBCompass"


# To Test the demo apps

curl --location --request POST 'http://localhost:8080/rice-production' --header 'Content-Type: application/json' --data-raw '{
    "area": "Brazil",
    "year": "1900",
    "unit": "tonnes",
    "value": "50000",
    "flag": "A",
    "flagDescription": "Official figure"
}'

curl --location --request GET 'http://localhost:8080/rice-production/area/Brazil'

curl --location --request GET 'http://localhost:8080/rice-production/662be9d22972e56692f5aa69'"# mogodb" 
