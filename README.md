# cloudera-cdh-setup


    1  ls
    2  sudo apt-get update
    3  curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
    4  sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
    5  sudo apt-get update
    6  sudo apt-cache policy docker-ce
    7  sudo apt-get install -y docker-ce
    8  history





docker pull cloudera/quickstart:latest

####### To start in deaemon mode

docker run --hostname=quickstart.cloudera --privileged=true -t -i -d --name cdh -p 8888:8888 -p 80:80 -p 7180:7180 cloudera/quickstart /usr/bin/docker-quickstart

###### To login to continer 

docker exec -it cdh bash

sudo /home/cloudera/cloudera-manager --express --force

#### Remove all stoped continers 

docker ps -aq --no-trunc -f status=exited | xargs docker rm



#### Spark-shell permission issue for root user ?

sudo -u hdfs hadoop fs -chmod 777 /user/spark
sudo -u spark hadoop fs -chmod 777 /user/spark/applicationHistory
