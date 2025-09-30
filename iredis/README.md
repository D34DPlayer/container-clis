# iredis-docker

Small docker image providing the [iredis](https://iredis.xbin.io/) command.

## Example usage

The documentation for `iredis` can be found on their website: https://iredis.xbin.io/

```bash
# Basic run
docker run --rm -ti \
    ghcr.io/d34dplayer/iredis:latest

# Database running on host
docker run --rm -ti \
    ghcr.io/d34dplayer/iredis:latest \
    -h host.docker.internal

# Connect to a database in a container
# Container "redis" in "my_network" network
docker run --rm -ti \
    --network my_network \
    ghcr.io/d34dplayer/iredis:latest \
    -h redis

# Bash function for easy access
iredis() {
    docker run --rm -ti \
        ghcr.io/d34dplayer/iredis:latest \
        "$@"
}

iredis -h host.docker.internal
```
