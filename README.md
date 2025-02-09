# Docker cheat sheet
## Docker Images

| Command | Usage |
| --- | --- |
| `docker pull <image>` | Get new image |
| `docker images` | See all pulled images |

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
| `docker ps -a` | See all containers|
| `docker run <container> --rm` | Start container and delete afterwards|
| `docker rm <container_id>` | Delete container|
| `docker container prune` | Delete stopped containers |
