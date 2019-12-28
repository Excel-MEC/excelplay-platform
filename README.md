
# excelplay-platform
Excel Play platform.


## Instructions to setup Development environment

1. `git clone --recurse-submodules https://github.com/Excel-MEC/excelplay-platform.git`
2. Install Docker and Docker-compose
3. docker-compose up


## Instructions for deploying

1. Install Docker
1. Clone the repository
```
`git clone --recurse-submodules https://github.com/Excel-MEC/excelplay-platform.git`
```
1. ```sudo docker-compose build```
1. ```sudo docker-compose up``` (You have to do this only once). After all the containers are started, quit ^c.
1. ```sudo docker-compose start ```(For starting all the containers)
1. (exec into auth django project)   
```
sudo docker exec -it <auth django image name> bash
```
1. cd to auth's manage.py directory
1. ```python manage.py collect static``` ( This will create static files in that directory. Move this to platform directory )

## Instructions for migrating django static files

1. exec into excelplay-auth container ( ```sudo docker exec -it <auth django image name> bash```)
2. cd to auth's manage.py directory.
3. python manage.py collect static ( This will create static files in that directory. Move this to platform directory )

## Some Usefull Docker Command

1. Status
```
sudo docker-compose ps
```
2. Logs
```
sudo docker-compose logs <container_name>
```
3. logs of the last n minutes
```
sudo docker-compose logs --since 2m <container_name>
```
4. To delete all containers (Useful when there is a cache problem)
```
sudo docker-compose stop
sudo docker system prune
```
5. To restart docker           
```
sudo docker-compose stop
sudo docker-compose start
```
Never use 'sudo docker-compose restart' to restart


