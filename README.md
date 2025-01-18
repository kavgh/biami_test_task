# Functionality

The BIAMI script is spinning out the docker compose file that contain BIAMI DEV program.

# Docker image

The docker image is builded from openjdk:8-jre-buster. Exposes 3 volumes `/opt/biami/bin/db`, `/opt/biami/bin/env` and `/opt/biami/bin/temp`. And runs command `/bin/bash` when container is created the command can be overrided.

# Docker compose file

The docker compose file is builds the docker image and creates docker container with 2 volumes binded `~/Downloads/bin/temp/db`, `~/Downloads/bin/env` and `~/Downloads/bin/temp` with `/opt/biami/bin/db`, `/opt/biami/bin/env` and `/opt/biami/bin/temp` respectively.

# BIAMI script

The BIAMI script accept 3 variables `db_dir`, `temp_dir` and `env_dir` it is the paths of directories that we want to bind with container. The paths must be escaped.
For example if we want to bind the `../temp/db` directory with `/opt/biami/bin/db` then we must pass `~\/path\/to\/your\/biami\/dir\/temp\/db` value to "db_dir" variable.

At the end the BIAMI script is upping the docker compose.

## !!!WARNING!!!

The DB directory must be separated from `../db` that is used by BIAMI to run this script.