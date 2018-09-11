This is a spark-jupyter docker container master. You can create spark cluster in your machines by following given instructions.

# Contains 
Docker slave-machine contains:
>  debian:stretch OS
>  python3.6.6
>  JAVA 8.181
>  HADOOP_VERSION 3
>  SPARK_VERSION 2.3.1
>  py4j

In addtion to what Docker slave-machine has, master-machine contains :
>  screen
>  vim
>  jupyter
>  pyspark

# CLONE
## git clone and docker pull for master on one machine
git clone https://github.com/somendra11/debian-spark-python3.6-master
docker pull somendra11/debian-spark-python3.6-master

## git clone and docker pull for master on the similar or a different machine
git clone https://github.com/somendra11/debian-spark-python3.6-slave
docker pull somendra11/debian-spark-python3.6-slave

# START
## MASTER
>  You have to go to master repo clone location and start docker by
sudo docker-compose up

## SLAVE
-  You have to go to slave repo clone location
-  Add your master machine ip in place of <MASTER_MACHINE_IP_HERE>
-  and start docker by
sudo docker-compose up
- For all slave machine
    -  sudo  docker ps -a (copy slave machine container id)
    -  sudo docker exec -it <CONTAINER_ID> bash
    - when your docker slave machine is up run
        >  echo "<MASTER_MACHINE_IP_HERE> master" >> /etc/hosts


# Run Jupyter in master
-  sudo  docker ps -a (copy master machine container id)
-  sudo docker exec -it <CONTAINER_ID> bash
-  screen -S jupyter
-  jupyter notebook
-  crl+a, then crl+d
-  exit
-  jupyter notebook will run on <MASTER_MACHINE_IP_HERE>:8022
-  jupyter notebook password will be abc123 (it can be changed)