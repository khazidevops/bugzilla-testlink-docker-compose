# bugzilla-testlink-docker-compose

Docker Compose - Bugzilla and TestLink

TestLink is a web based application to manage manual tests along with software life cycle. Tests may vary from simple steps to more evolved process, but each will provide simple steps to follow.

Prerequisites

Docker Engine 18.06.0+

Linux: Follow all the steps present in the official documentation
Docker Compose 1.22.0+

Follow all the steps present in the official documentation
Set the environment variables

The file .env.example contains all the environment variables required.

Copy and paste with the file .env.example with the name .env to make the Docker Compose use the environment variables defined in this file:

cp .env.example .env
After that, setup the variables according to specific requirements of each deployment.

Building and Deploying the containers

docker-compose up --build
It will build the containers and run the platform as specified in the file docker-compose.yml, opening a log screen with the logs of all the services started.

Stopping the execution

If you are still in the log screen press Ctrl + C just one time for graceful stop, two times to force stop

To stop all containers created by docker-compose, you need to go to the folder where docker-compose.yml is and run:

docker-compose down
To stop just one container:

docker stop my_container
Other useful commands

Restarts Docker. Useful in critical situations:

sudo service docker restart
Check all containers and its status:

docker container ls
Enter in the shell or bash of a particular container:

docker exec -it container_id /bin/bash
Stop all containers:

docker stop $(docker ps -a -q)
Delete all containers:

docker rm -f $(docker ps -a -q)
Delete all volumes:

docker volume rm $(docker volume ls -q)
Delete all container images:

docker rmi -f $(sudo docker images -q)
