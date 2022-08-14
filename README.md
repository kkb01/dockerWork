# Docker Work

## Notes for docker

- Docker **start** command will start any stopped container. If you used docker **create** command to create a container, you can start it with this command. Docker **run**  command is a combination of create and start as it creates a new container and starts it immediately.

- **"docker system prune"** command will delete all stopped containers.
- The **docker stop** commands issue the **SIGTERM** signal, whereas the docker kill commands sends the **SIGKILL** signal. The execution of the **SIGTERM** and **SIGKILL**. is different. Unlike SIGKILL, the SIGTERM gracefully terminates a process rather than killing it immediately. It is possible to handle, ignore or block a **SIGTERM** signal, but a **SIGKILL** signal cannot be blocked or handled. **SIGTERM** allows a child process or parent process the opportunity to send information to other processes.
- Use of **it** flag with **docker exec -it** command | **docker exec -it**. Runs a new command in a running container.

**

## Docker-Compose

 - Seperate CLI that gets installed along with Docker
 - Used to Start up multiple docker containers at the same time
 - Automates some of the long-winded arguments we were passing to **'docker-run'**

**Sample Docker-Compose.yml file

```json
version: '3'
services: 
  redis-server:
    image: 'redis'
    restart: always
  node-app:
    restart: always
    build: .
    ports:
      - "8080:8080"
```

`docker run myimage` 

**`docker-compose up`-`**

    docker build .    
    docker run myimage 
  **`docker-compose up --build`**
  
**`docker ps`** :  list all the running containers
**`docker-compose ps`** : list all the running containers associated in **`docker-compose.yml`** file. **(Must run on directory where the docker-compose.yml located)**
Stop all the containers created by docker-compose.yml

    docker-compose down
**Docker Restart Policies:** There are four restart policies

 1. **"no"** 		: Never attempt to restart this . container if it stops or crashes.
 2. **"always"** : If this container stops ***for any reason*** always attempts to restart it.
 3. **"on-failure"**	: Only restarts if container stops with an error code.
 4. **"unless-stopped"**	: Always restarts unless we (*the developers*) forcibly stop it.

