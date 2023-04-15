DOCKER

docker images
docker ps --size
docker ps
docker exec -it <container_name_or_id> psql -U postgres
docker cp portal_db_1:/path/to/mydb.backup /backups/
docker-compose config --services portal_web_1 > portal_web_1.yml
docker inspect -f '{{json .Mounts}}' 9876764ed8da | jq '.[] | select(.Destination=="DESTINATION_PATH") | .Source'
docker inspect -f '{{json .Mounts}}' aec033bc07a4
docker cp portal_php_1:var/www/html $(pwd)
docker exec portal_web_1 ls /portal
docker exec 9876764ed8da find / -name site.conf 2>/dev/null
docker exec -it portal_web_1 sh 

docker commit <dockername> dock1  #dock1 any name
docker save -o docker.tar dock1
docker load -i docker.tar         #load docker

docker images
docker run --name portal_web_1 -p 80:80 -p 443:443 -d php
docker run -p 80:80 -p 443:443 -d php
docker run -d -p 9000:9000/tcp php

docker exec -it 74dec3d16bd4 /bin/bash
docker start 5911c414d121
docker run --rm -d image
docker logs container_name_or_id
docker inspect container_name_or_id

docker stop 5911c414d121
docker rm 5911c414d121
or
docker rm -f 5911c414d121
