# Burhan-hotel-booking-and-management
A Hotel booking and management platform
### Local setup

- Create a network bridge

```
docker network create my-app-network

```
- build spring boot

```
docker build -t spring-backend .

```
- run container
```
docker run -d --name spring-backend --network my-app-network -p 4040:4040 spring-backend

```
- build react


```
docker build -t react-frontend .

```
- run react
```
docker run -d --name react-frontend --network my-app-network -p 7070:7070 -e REACT_APP_API_URL=http://spring-backend:4040 react-frontend

```
- database will be local mysql that we used for development so no need extra setup for db
- test setup

```
docker exec -it react-frontend sh
# Inside the container
curl http://spring-backend:4040

```

- application.properties

```
spring.application.name=PhegonHotel
#MYSQL CONNECTION
server.port=4040
spring.datasource.url=jdbc:mysql://localhost:3306/hotel_db
spring.datasource.username=root
spring.datasource.password=12345
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQLDialect

spring.jpa.hibernate.ddl-auto=update



aws.s3.secret.key=your secret key
aws.s3.access.key=your access key
hotel-mongo=your bucket name

```
