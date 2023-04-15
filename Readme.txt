DOCKER

docker images
docker ps --size
docker ps
docker exec -it <container_name_or_id> psql -U postgres
docker cp portal_db_1:/path/to/mydb.backup /backups/
docker-compose config --services portal_web_1 > portal_web_1.yml
docker inspect -f '{{json .Mounts}}' 9876764ed8da | jq '.[] | select(.Destination=="DESTINATION_PATH") | .Source'
docker inspect -f '{{json .Mounts}}' aec033bc07a4

