# cloudera-cdh-setup


docker pull cloudera/quickstart:latest

####### To start in deaemon mode

docker run --hostname=quickstart.cloudera --privileged=true -t -i -d --name cdh -p 8888:8888 -p 80:80 -p 7180:7180 cloudera/quickstart /usr/bin/docker-quickstart

###### To login to continer 

docker exec -it cdh bash


#### Remove all stoped continers 

docker ps -aq --no-trunc -f status=exited | xargs docker rm