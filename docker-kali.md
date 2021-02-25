launch command

`docker run --name kali_linux --net="host" --privileged -e DISPLAY=$DISPLAY -it -v /tmp/.X11-unix:/tmp/.X11-unix kalilinux/kali-linux-docker /bin/bash`

meta packages

`apt-get update && apt-cache search kali-linux`

persistent storage

`docker run -ti --rm --mount src=kali-root,dst=/root --mount src=kali-postgres,dst=/var/lib/postgresql my-kali`

## Reference
1 https://hackingprofessional.github.io/Security/Using-Kali-Linux-as-a-Docker-container
1 https://airman604.medium.com/kali-linux-in-a-docker-container-5a06311624eb
