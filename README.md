# Build aport packages using docker

This docker image simplifies the building of aport images for x86_64.

Everthing required to build a package is in the image, so the host system is not modified in any way.

Usage:

* checkout aports
* change into aports directory
* run:

```
docker run -it --rm \
  -v $(pwd):/aports \
  -v $(pwd)/packages:/home/build/packages \
  --user build --workdir /aports \
  micwy/aport-builder-x86_64:latest \
  /build.sh testing/mypackage
```

* The package will be in the "packages" sub directory
