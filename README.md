# Docker Project

Project for the **Dockerfiles** and **Docker Compose** sections

## Initial configuration

- Create account at the https://unsplash.com
- At the https://unsplash.com/oauth/applications create new **demo** application with title **"Images Gallery"**.
  Demo applications are limited to 50 requests per hour
- In the newly created application find section **"Keys"** and copy **Access Key**
- In the **api** folder create file **.env.local** and add there following line:

```
UNSPLASH_KEY=<Paste copied Access Key here>
```

**EXAMPLE** with fake code(don't try to use it in your app):

```
UNSPLASH_KEY=2MJvApIkV13hfg2LmQlneILfHoJ2ttlzSdPKefGOyKM
```

## Create custom network 
```
docker network create image-gallery-network 
```
## RUN FRONT END APP DOCKER
```
# docker build -t einsteinnwizu/image-gallery-frontend:v1 .
# docker run -d --name image-gallery-frontend-con --network image-gallery-network -p 3000:80 einsteinnwizu/image-gallery-frontend:v1
```

## RUN BACKEND api APP DOCKER
```
# docker build -t einsteinnwizu/image-gallery-backend:v1 .
# docker run -d --name image-gallery-backend-con --network image-gallery-network -p 5050:5050 einsteinnwizu/image-gallery-backend:v2
```

