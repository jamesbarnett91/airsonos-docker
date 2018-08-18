# Airsonos Docker Images
Docker images for the now defunct [Airsonos project](https://github.com/stephen/airsonos), which provides AirPlay support for all Sonos speakers. These images are the easiest way to get Airsonos running on both x86 and ARM devices.

The currently published NPM version of Airsonos does not support iOS 9+ devices. A fix for this is included in these images, via the mounted helper.js file.

## Usage
There are 2 different images available, depending on if you want to run on x86 or ARM architecture. 
If you don't know which to use, the x86 is probably the one you want.

Airsonos must be run using [host networking](https://docs.docker.com/network/host/), to allow access to the Sonos devices on your network from within the container.

### x86
```
$ docker run -d --name airsonos --network=host jbarnett/airsonos
```

### arm32v7 (e.g. Raspberry Pi 2 and 3)
```
$ docker run -d --name airsonos --network=host jbarnett/airsonos:arm32v7
```

## Note
I didn't bother trying to optimise the image size and as a result they're around 800mb. The base image is Debian Jessie which you may already have a cached layer for anyway.
I might rebuild them using Alpine at some point.
