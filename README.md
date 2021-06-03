# blue-whale

A Docker factory: containing templated dockerfiles, cross compiling docker 
images. Including CMake, Qt5

## Configuring
Configure the templated Dockerfile.in into Dockerfiles using jq and sed.
The configure script will replace all the %%KEYWORD%% keys with the correct 
values. The script will also 'copy-and-paste' the contents of the include 
files where it finds the #include keywords. 

_Note: the paths are relative to where the script is run, that's why we have
"include/file.name" style since it is intended to be run from the top level
directory._

``` bash
    # install jq
    $ sudo apt install jq
    $ ./configure

    # or build and run the jq image
    $ docker build -t jq tools/jq
    $ docker run --rm -v $PWD:$PWD -w $PWD jq ./configure
```

## Building
Build the docker images
``` bash
    # read help
    $ make help

    # build base image
    $ make base

    # build qt5 image
    $ make qt5

    # build cross-compile base image
    $ make xc-base-arm64

    # build cross-compile qt5 image
    $ make xc-qt5-arm64

    # build all images
    $ make all
```

## Publish
Push the docker images
``` bash
    # TODO
```
