Infrastructure with Docker
   - Install Docker and Docker compose
   - create two containers with a docker:
        Apache / PHP using the ubuntu docker image: 16.04 on the Docker Hub, exposed port: 80
        Mysql using the ubuntu docker image: 16.04 on the Docker Hub, exposed port: 3306
   - Create link between the two containers
   - Create volumes for the two containers
        - apache: volume where there will be a php application / script
        - mysql: volume for mysql "data" folder
   - Deploy for a php application / script

###Ubuntu Instance-Prerequisites

            -sudo usermod -a -G sudo "user"    #add user to the group sudo
            -sudo visudo
            -"user" ALL=(ALL) NOPASSWD: ALL  #remove password for sudo commands


            -apt-get update -y
            -apt-get upgrade -y
            -apt-get install openssh-server -y
            -apt-get install git -y
            -apt-get install net-tools -y
            -apt-get install \
                -apt-transport-https \
                -ca-certificates \
                -curl \
                -software-properties-common

            -apt-get install vim
            -apt-get install docker -y ; apt-get install docker.io -y ; apt-get install docker-compose -y ;

            -docker-compose up --build -d
