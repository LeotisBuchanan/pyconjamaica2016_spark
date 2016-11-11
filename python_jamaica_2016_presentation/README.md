# Getting started

Minimum Requirements

- Linux system(Ubuntu, Centos or Debian)
- Docker installed
- Internet connection
- firefox/chrome browser installed

This was tested on a Mac Book pro with the following features:

OS: Ubuntu 16.10(yes Ubuntu on a Mac :-) )
Processor: Intel Quad Core
Memory: 16GB

## Instructions

1.Download the Docker Image

    Run the following command at the shell to download the docker image

    1. docker pull hessian/yardman

2.start the docker image by running the following command

   docker run --rm -p 8080:8080 hessian/yardman


3. This should start the image and login you into the docker container

4. change to the pycon user, by entering the following command

   su pycon

5. change to the pycon home folder by entering the following command

   cd /home/pycon

6. start zeppelin by entering the follow command

   ./start-zeppelin.sh

7. This should start zeppelin

8. Enter the url localhost:8080 in your browser. If all went well you should see the zeppelin ui.
