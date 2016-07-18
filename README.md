# docker-rok4-with-data

Docker composition configuration to deploy Nginx, Rok4 and two data pyramids

## Description

This repository contains :
* A docker-compose configuration
* A Nginx configuration

The docker-compose configuration contains :
* A Nginx server (docker image [nginx](https://hub.docker.com/_/nginx/) )
* A Rok4 server (docker image [rok4/rok4](https://hub.docker.com/r/rok4/rok4/) )
* 2 data pyramids (docker images [rok4/data-scan1000](https://hub.docker.com/r/rok4/data-scan1000/) and [rok4/data-bdortho-d075](https://hub.docker.com/r/rok4/data-bdortho-d075/) )

The Nginx configuration redirect requests on port 80, path /rok4 to rok4, port 9000

## Requirements

Have an host with docker engine and docker-compose installed, a working connection

## Use

To run the application, in the main directory :
docker-compose up

To test if the server is well running, go to your browser and type this URI : 

    [http://127.0.0.1:1234/rok4?SERVICE=WMS&REQUEST=GetMap&VERSION=1.3.0&LAYERS=ORTHO_JPG_PM_D075&STYLES=normal&CRS=EPSG:3857&WIDTH=3000&HEIGHT=3000&BBOX=242152,6229923,291072,6264167&FORMAT=image/png]

This should work!


### Change the listening port

To change the listening port on the host (1234 by default), change the line in the file `docker-compose.yml` :

    nginx:
    image: nginx
    ports:
      - "1234:80" <----------------




