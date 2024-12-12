# Images

The Images view lets you manage Docker images without having to use the CLI. By default, it displays a list of all Docker images on your local disk.

## Pull an image

Supports pulling from added image repositories, equivalent to the `docker pull` operation.

!!! tips "Tips"
    Pulling an image may take some time. If you want to view the pull logs after closing the drawer, you can find the log file at `/opt/1panel/tmp/docker_logs/image_pull_[image name]_[timestamp].log`.

## Import an image

Import images from a file on the 1Panel server, which is equivalent to the `docker load` operation.

## Build an image

You can directly edit the Dockerfile or select a Dockerfile from the server to build an image, equivalent to the `docker build` operation.

!!! tips "Tips"
    Pulling an image may take some time. If you want to view the pull logs after closing the drawer, you can find the log file at `/opt/1panel/tmp/docker_logs/image_build_[image name]_[timestamp].log`.

## Push an image to the registry

This action allows you to push an image to the container registry, which is equivalent to the `docker tag` and `docker push` operation.

## Remove images

You can directly delete specific images from the image list, or click the `Prune` button to clean up dangling images or all unused images.

## Export an image

Exports the image as a .tar file, equivalent to the `docker save` operation.
