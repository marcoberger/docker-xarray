# Dockerized xarray sample

This sample show how to execute a python script, which uses the xarray library within a simple docker container.

## Prerequesites
- Docker install with version 20.0 or above

## Clone repository
1. Install git on your computer
2. Checkout repository: $ `git checkout ...`

## Run docker container plus sctipt
Steps to start the container and execute script:

1. start docker deamon or start Docker desktop application
2. run commands:

```bash
cd ${PROJECT_ROOT_FOLDER}
docker-compose up
```

Check the console output for _hello123_, which is echoed by the python script.

## Included files in the project
- _geodata/test.txt_: The geo-data file to be read from a docker volume. The folder _geodata/_ is mounted as volume _/mygeodata_ in docker image. See _docker-compose.yml_ on line 6.
- _src/script.py_: The python script that is run in the container. See _ENTRYPOINT_ on line 12 in _Dockerfile_
- _requirements.txt_: Requirements to be installed in the docker image. See lines 5-8 in _Dockerfile_
- _Dockerfile_: Describes how the docker image is built. Only happens once - not for each execution of the container.
- _docker-compose.yml_: Comfort docker tool to start the container and mount the volume.
 