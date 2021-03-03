# demo-container
install docker desktop
for mac/windows10 (except home edition) --> https://www.docker.com/products/docker-desktop

for windows10 home edition --> https://docs.docker.com/docker-for-windows/install-windows-home/

# basic command
docker info

docker container list -a

docker ps

docker image list -a


# create postgresql with persistence
docker run -p 5432:5432 --name postgres -e POSTGRES_PASSWORD=docker -e POSTGRES_USER=docker -e POSTGRES_DB=docker -d -v /Users/ckongman/work/postgresql/data:/var/lib/postgresql/data postgres

test command

docker ps

docker exec -it postgres bash

psql -U docker

\l

\dt

\z

select * from employee;

\q

exit

docker container stop postgres

docker container start postgres

Retry query again

docker exec -it postgres bash

psql -U docker

\l

\q

exit

remove command / use docker desktop ui

docker container rm [container name1] [container name2] [...]

docker rmi -f [container name1] [container name2] [...]

# Code 
git clone https://github.com/chatapazar/demo-container.git demo

Edit application.properties

From localhost to postgres

mvn spring-boot:run

PostMan Test

insert : http://localhost:8080/api/v1/employees

POST : { "name": "tiger", "age":12 }

getall : http://localhost:8080/api/v1/employees

GET : 


mvn clean package -DskipTests

Java -jar demo*.jar

docker build ./ -t myapp

docker run -p 8080:8080 myapp

docker run -d -p 8080:8080 myapp

Edit application.properties

From localhost to postgres

mvn clean package -DskipTests

docker build ./ -t myapp

clear docker myapp & postgres with docker desktop

docker-compose up




