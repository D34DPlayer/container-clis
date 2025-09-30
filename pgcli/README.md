# pgcli-docker

Small docker image providing the [pgcli](https://www.pgcli.com/) command.

## Example usage

The documentation for `pgcli` can be found on their website: https://pgcli.com/

```bash
# Basic run
docker run --rm -ti \
    ghcr.io/d34dplayer/pgcli:latest

# Database running on host
docker run --rm -ti \
    ghcr.io/d34dplayer/pgcli:latest \
    -h host.docker.internal

# Connect to a database in a container
# Container "database" in "my_network" network
docker run --rm -ti \
    --network my_network \
    ghcr.io/d34dplayer/pgcli:latest \
    -h database

# With configuration and persistent history
docker run --rm -ti \
    -v $HOME/.config/pgcli:/root/.config/pgcli \
    ghcr.io/d34dplayer/pgcli:latest

# Bash function for easy access
pgcli() {
    docker run --rm -ti \
        -v $HOME/.config/pgcli:/root/.config/pgcli \
        ghcr.io/d34dplayer/pgcli:latest \
        "$@"
}

pgcli -h host.docker.internal
```
