## how to build image
docker build -t hessian/yardman .

##tag image
docker tag 1b21cb7996a3  hessian/yardman

## push image the docker hub
docker push hessian/yardman



##how to install docker


##how to pull image
docker pull hessian/yardman

##running image
docker run --rm -p 8080:8080 hessian/yardman

## running with interactive bash
 docker run -it <image> /bin/bash
docker run -it --rm -p 8080:8080 hessian/yardman /bin/bash
## commit image changes
docker commit container_id hessian/yardman
