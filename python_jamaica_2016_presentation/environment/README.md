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
