# Set up PostgreSQL database using Docker on Windows

The purpose of this project is to set up PostgreSQL database using Docker on Windows.
1. Install [Docker Destop](https://docs.docker.com/desktop/windows/install/) on Windows
2. Create a container named PostgresData based on the Alpine image

```
docker create -v /var/lib/postgresql/data --name PostgresData alpine
```
3. Create a container named postgres-spring using PostgresData container with postgres:alpine image

```
docker run -p 5432:5432 --name postgres-spring -e POSTGRES_PASSWORD=password -d --volumes-from PostgresData postgres:alpine 
```

<img src="https://github.com/kmjenniferng/postgreSQL-docker-windows/blob/main/screenshot-1.png">

4. Execute the container named postgres-spring in Bash mode
```
docker exec -it 6a2a91bbaa94 bin/bash
```
5. Login to PostgreSQL database
```
psql -U postgres
```
6. Create database named springbootdemodb
```
CREATE DATABASE springbootdemodb;
```
7. Show the list of databases
```
\l
```
8. Connect to database named springbootdemodb
```
\c springbootdemodb
```

<img src="https://github.com/kmjenniferng/postgreSQL-docker-windows/blob/main/screenshot-2.png">
