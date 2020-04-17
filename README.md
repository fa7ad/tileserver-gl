![tileserver-gl](https://cloud.githubusercontent.com/assets/59284/18173467/fa3aa2ca-7069-11e6-86b1-0f1266befeb6.jpeg)


# TileServer GL
[![Build Status](https://travis-ci.org/maptiler/tileserver-gl.svg?branch=master)](https://travis-ci.org/maptiler/tileserver-gl)
[![Docker Hub](https://img.shields.io/badge/docker-hub-blue.svg)](https://hub.docker.com/r/maptiler/tileserver-gl/)

Vector and raster maps with GL styles. Server side rendering by Mapbox GL Native. Map tile server for Mapbox GL JS, Android, iOS, Leaflet, OpenLayers, GIS via WMTS, etc.

## Slim
This image is a repackaging of the original tileserver-gl image using node's slim image as the base

## Get Started
Download an `.mbtiles` file from a source like [OpenMapTiles](https://openmaptiles.com/).

Install [Docker](https://www.docker.com/) on your computer and then run in the directory with the downloaded MBTiles the command:

```bash
docker run --rm -it -v $(pwd):/data -p 8080:80 fa7ad/tileserver-gl-slim
```

This will download and start a ready to use container on your computer and the maps are going to be available in webbrowser on localhost:8080.

### docker-compose
You can use a docker-compose file instead of running the long command every time.

Here's an example Compose file that you can follow:
```yml
version: "3"

services:
  mapserver:
    image: fa7ad/tileserver-gl-slim:latest
    volumes:
      - "./mbtiles:/data"
    ports:
      - "8080:80"
    expose:
      - 80
```

In the example abobe, `./mbtiles` is the directory containing your `.mbtiles` file.

## Documentation
Functionally, this image is the exact same software as tileserver-gl. So you can follow the full documentation of tileserver-gl at https://tileserver.readthedocs.io/.
