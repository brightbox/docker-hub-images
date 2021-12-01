# Brightbox Docker Containers

This repository automatically builds docker containers containing tools
to access Brightbox Cloud.

* Brightbox Cloud CLI

The docker containers are built once a day, ensuring you always have
the latest tools available. Just replace your usual command line with
the equivalent `docker run` command.

### Brightbox Cloud CLI Usage

[Brightbox Cloud CLI](https://www.brightbox.com/docs/guides/cli/)
requires a working directory which can store the config. You can map
any directory you like, or you can co-opt the default one created by a
local cli command. You can use this directory with the following:
```shell
docker run -it --user $(id -u):$(id -g) -e "HOME=$HOME" -v ~/.brightbox:$HOME/.brightbox brightbox/cli <command>
```

For example:
```shell
docker run -it --user $(id -u):$(id -g) -e "HOME=$HOME" -v ~/.brightbox:$HOME/.brightbox brightbox/cli accounts
```

```shell
docker run -it --user $(id -u):$(id -g) -e "HOME=$HOME" -v ~/.brightbox:$HOME/.brightbox brightbox/cli server create img-6xysw
```
