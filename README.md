# Docker cheat sheet
## Docker Images

| Command | Usage |
| --- | --- |
| `docker pull <image>` | Get new image |
| `docker images` | View present images |
| `docker search <image>` | Search Docker Hub images |

## Docker Container
| Command | Usage |
| --- | --- |
| `docker run <container>` | Start new container |
| `docker run --name <name> <container>` | Start new container and refer it by name |
| `docker run -d` | Start container and detach |
| `docker run <container> <cmd>` | Start container and run cmd |
| `docker run -it <container> <cmd>` | Start container and run cmd interactively|
| `docker run -P <container> <cmd>` | Start container and publish all ports (using `docker port <name>`)|
| `docker run -p 8888:80 <container> <cmd>` | 8888: exposed port for Host, 80: internal port for web server in container|
| `docker run <container> --rm` | Start container and delete afterwards|
| `docker ps -a` | See all containers|
| `docker stop <id>` | Stop container |
| `docker rm <id>` | Delete container|
| `docker container prune` | Delete stopped containers |
| `docker container ls` | View containers |
| `docker container logs <name>` | Logs for container (useful when detached) |
| `docker build -t <yourusername/container> .`| Build docker image from source. Ensure `Dockerfile`. Output in `docker images` |
| `docker push <yourusername/container>` | Publish image on Docker Hub. Ensures login |

## Dockerfile cheatsheat
```dockerfile
# base image
FROM python:3.8

# set a directory for the app
WORKDIR /usr/src/app

# copy all the files to the container
COPY . .

# install dependencies
RUN pip install --no-cache-dir -r requirements.txt

# define the port number the container should expose
EXPOSE 5000

# run the command
CMD ["python", "./app.py"]
```
This is then run as `docker run -p 8888:5000 <container>`
