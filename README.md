# Docker Fuzzy Run

docker-frun is a Docker CLI plugin that adds the `frun` subcommand to the Docker CLI.
This plugin allows users to delay the selection of containers to be launched.
Therefore, users can select the image to use after deciding on the container launch options and command line arguments.

## Requires

- docker (20.10.24 and 28.2.2 are tested)
- fzf

## Usage

docker-frun accepts almost the same arguments as the docker run command, but
requires the `--` as an image, and allows you to select the image to use with
fzf.

```
$ docker frun -it --rm -- cat /etc/lsb-release

  ca2b0f26964c    77.9MB ubuntu:jammy-20240227
▌ 52882761a72a    77.9MB ubuntu:jammy
  2/46 ---------------------------------------
> ubuntu

DISTRIB_ID=Ubuntu
DISTRIB_RELEASE=22.04
DISTRIB_CODENAME=jammy
DISTRIB_DESCRIPTION="Ubuntu 22.04.4 LTS"
```

For details see `docker frun --help`.

### Key bindings

- ctrl-j/ctrl-k
    
    Scroll the preview window up and down.


## Install

Put `docker-frun` in a Docker CLI Plugin directory (e.g., `~/.docker/cli-plugins/` or `/usr/local/lib/docker/cli-plugins/`) and add 'x' permission to that file.

```
cp docker-frun ~/.docker/cli-plugins/
chmod +x ~/.docker/cli-plugins/docker-frun
```

## Uninstall

Just remove `docker-frun` from your environment.

```
rm ~/.docker/cli-plugins/docker-frun
```

