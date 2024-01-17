# Docker-todo-app

### Learning from this project
1. how to create **docker image**
2. how to security concern with using low previleges.
3. how to upload only important file to docker by using **.dockerignore**
---
### To run this project
1. clone this repository and enter this repository.
```
git clone https://github.com/tusharnagar17/docker-todo-app.git && cd docker-todo-app
```

2. build and then run 
```
docker build . -t docker-todo-app

docker run -it -p 3000:3000 docker-todo-app
```

3. sent GET request to localhost:3000
---

## Here the main file `Dockerfile`
```
FROM node:16
  
WORKDIR /usr/src/app

COPY --chown=node:node . .
RUN npm ci 

ENV DEBUG=playground:*
  
USER node
CMD npm start
```