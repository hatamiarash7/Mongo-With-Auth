# Mongo with authentication

A Docker Image for MongoDB which makes it easy to create an Admin, a Database and a Database User when the container is first launched.

It's an updated version of [docker-mongo-auth](https://github.com/aashreys/docker-mongo-auth). That's not updated anymore.

## Customization

There are a number of environment variables which you can specify to customize the username and passwords of your users.

- With Dockerfile

```dockerfile
# ENV AUTH yes

# ENV MONGODB_ADMIN_USER admin
# ENV MONGODB_ADMIN_PASS adminpass

# ENV MONGODB_APPLICATION_DATABASE testdatabase
# ENV MONGODB_APPLICATION_USER testuser
# ENV MONGODB_APPLICATION_PASS testpass
```
  
- With docker-compose.yml

```yaml
services:
  db:
    image: hatamiarash7/mongo-auth:latest
    environment:
      - AUTH=yes
      - MONGODB_ADMIN_USER=admin
      - MONGODB_ADMIN_PASS=adminpass
      - MONGODB_APPLICATION_DATABASE=testdatabase
      - MONGODB_APPLICATION_USER=testuser
      - MONGODB_APPLICATION_PASS=testpass
```

- With command line

```bash
docker run -it \
  -e AUTH=yes \
  -e MONGODB_ADMIN_USER=admin \
  -e MONGODB_ADMIN_PASS=adminpass \
  -e MONGODB_APPLICATION_DATABASE=testdatabase \
  -e MONGODB_APPLICATION_USER=testuser \
  -e MONGODB_APPLICATION_PASS=testpass \
  -p 27017:27017 hatamiarash7/mongo-auth:latest
```