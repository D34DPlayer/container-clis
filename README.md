# litecli-docker

Small docker image providing the [litecli](https://litecli.com/) command.

## Example usage

The documentation for `litecli` can be found on their website: https://litecli.com/

```bash
# Connect to a local database
docker run --rm -ti \
    -v $(pwd)/unicorns.db:/mnt/unicorns.db \
    d34dplayer/litecli:latest \
    /mnt/unicorns.db

# Connect to a database in a volume
docker run --rm -ti \
    -v unicorn-data:/mnt \
    d34dplayer/litecli:latest \
    /mnt/unicorns.db

# With configuration and persistent history
docker run --rm -ti \
    -v $HOME/.config/litecli:/root/.config/litecli \
    -v $(pwd)/unicorns.db:/mnt/unicorns.db \
    d34dplayer/litecli:latest \
    /mnt/unicorns.db

# Bash function for easy access
litecli() {
    test -z "$1" && echo Missing db path && return 1
    NORMALIZED_PATH=$(realpath "$1")

    docker run --rm -ti \
        -v $HOME/.config/litecli:/root/.config/litecli \
        -v $NORMALIZED_PATH:/mnt/database.db \
        ghcr.io/d34dplayer/litecli:latest \
        /mnt/database.db
}
```