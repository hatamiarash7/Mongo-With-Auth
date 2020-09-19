# Mongo with authentication

[![GitHub license](https://img.shields.io/github/license/hatamiarash7/Mongo-With-Auth)](https://github.com/hatamiarash7/Mongo-With-Auth/blob/master/LICENSE) ![Github](https://github.com/hatamiarash7/Mongo-With-Auth/workflows/Github/badge.svg) ![Dockerhub](https://github.com/hatamiarash7/Mongo-With-Auth/workflows/Dockerhub/badge.svg) ![Docker Image Size (latest by date)](https://img.shields.io/docker/image-size/hatamiarash7/mongo-auth)

A Docker Image for MongoDB which makes it easy to create an Admin, a Database and a Database User when the container is first launched.

It's an updated version of [docker-mongo-auth](https://github.com/aashreys/docker-mongo-auth). That's not maintain anymore.

## Customization

There are multiple environment variables which you can specify to customize the username and passwords of your users.

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

## Support

[![ko-fi](https://www.ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/D1D1WGU9)

<div><a href="https://payping.ir/@hatamiarash7"><img src="https://cdn.payping.ir/statics/Payping-logo/Trust/blue.svg" height="128" width="128"></a></div>

## Contributing

1. Fork it !
2. Create your feature branch : `git checkout -b my-new-feature`
3. Commit your changes : `git commit -am 'Add some feature'`
4. Push to the branch : `git push origin my-new-feature`
5. Submit a pull request :D

## Issues

Each project may have many problems. Contributing to the better development of this project by reporting them.
