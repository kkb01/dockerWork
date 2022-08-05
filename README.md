# dockerWork

## Notes for docker

- Docker **start** command will start any stopped container. If you used docker **create** command to create a container, you can start it with this command. Docker **run**  command is a combination of create and start as it creates a new container and starts it immediately.

- **"docker system prune"** command will delete all stopped containers.
- The **docker stop** commands issue the **SIGTERM** signal, whereas the docker kill commands sends the **SIGKILL** signal. The execution of the **SIGTERM** and **SIGKILL**. is different. Unlike SIGKILL, the SIGTERM gracefully terminates a process rather than killing it immediately. It is possible to handle, ignore or block a **SIGTERM** signal, but a **SIGKILL** signal cannot be blocked or handled. **SIGTERM** allows a child process or parent process the opportunity to send information to other processes.
