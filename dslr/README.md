# dslr-docker

Small docker image providing the [dslr](https://github.com/mixxorz/DSLR) command.

## Example usage

The documentation for `dslr` can be found on their repository: https://github.com/mixxorz/DSLR

```bash
# Basic run
docker run --rm -ti \
    ghcr.io/d34dplayer/dslr:latest

# Database running on host
## Via the host domain
docker run --rm -ti \
    ghcr.io/d34dplayer/dslr:latest \
    -h host.docker.internal
## With host networking
docker run --rm -ti \
    --network host \ 
    ghcr.io/d34dplayer/dslr:latest \
    -h localhost

# Connect to a database in a container
# Container "postgres" in "my_network" network
docker run --rm -ti \
    --network my_network \
    ghcr.io/d34dplayer/dslr:latest \
    -h postgres

# Supporting dump export/imports
docker run --rm -ti \
    --volume `pwd`:/mnt \
    ghcr.io/d34dplayer/dslr:latest \
    -h postgres

# Bash function for easy access
dslr() {
    docker run --rm -ti \
        --network host \
        --volume `pwd`:/mnt \
        ghcr.io/d34dplayer/dslr:latest \
        "$@"
}

dslr -h host.docker.internal
```
