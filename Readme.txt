DOCKER

docker images
docker ps --size
docker ps
docker exec -it 6820ea0bb3ba psql -U postgres
docker cp portal_db_1:/path/to/mydb.backup /backups/
docker-compose config --services portal_web_1 > portal_web_1.yml
docker inspect -f '{{json .Mounts}}' 9876764ed8da | jq '.[] | select(.Destination=="DESTINATION_PATH") | .Source'
docker inspect -f '{{json .Mounts}}' aec033bc07a4
docker cp portal_php_1:var/www/html $(pwd)
docker exec portal_web_1 ls /portal
docker exec 6820ea0bb3ba find / -name site.conf 2>/dev/null
docker exec -it portal_web_1 sh 



docker commit <dockername> dock1  #dock1 any name
docker save -o docker.tar dock1
docker load -i docker.tar         #load docker
docker run --name portal_web_1 -p 80:80 -p 443:443 -d php


docker images
docker run --name portal_web_1 -p 80:80 -p 443:443 -d php
docker run -p 80:80 -p 443:443 -d php
docker run -d -p 9000:9000/tcp php

docker exec -it 74dec3d16bd4 /bin/bash
docker start 5911c414d121
docker run --rm -d image
docker start portal_web_1

docker logs container_name_or_id
docker inspect container_name_or_id
docker inspect portal_web_1 > portal_web_1-config.json
docker logs 6820ea0bb3ba

docker stop 5911c414d121
docker rm 5911c414d121
or
docker rm -f 5911c414d121



docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' 8dc42e5bd2e5           #Gets container ip addr
docker inspect -f '{{range .NetworkSettings.Networks}}{{.GlobalIPv6Address}}{{end}}' 8dc42e5bd2e5   #ip for ipv6


Nē. Vajadzētu bekapot docker run konfigu, lai var docker-compose pēc tam uztaisīt, kā arī datus, kurus izmanto docker konteineri (mounti).

docker exec 8dc42e5bd2e5 pg_dumpall -U postgres > BACK.sql
pg_restore -U postgres -d joomladb BACK.sql


POSTGRES

sudo -u postgres psql -c "ALTER USER postgres PASSWORD 'newpassword';"


\l                 #list all db's
\c [database_name]
\du                             #This command shows a list of all users in the current 
\q                      #exit

    SELECT * FROM pg_stat_activity;     #list all current sessions (known as "backends") that are connected to database
    SELECT usename FROM pg_user;        #list of all users that are defined in the database system.
    SELECT datname, usename FROM pg_user JOIN pg_database ON usesysid = pg_database.datdba WHERE datname = current_database();
                                                       #list of all users that have connect permission on the current database.
    SELECT * FROM pg_user WHERE usesuper = true;  #check for all superusers
    
CREATE ROLE admin;                                       #create admin role
GRANT ALL PRIVILEGES ON DATABASE mydatabase TO admin;    #grant privileges to roles

CREATE ROLE user;                                        #create user role
GRANT SELECT ON TABLE mytable TO user;                   #grant privileges to roles
GRANT SELECT, INSERT, UPDATE ON TABLE mytable TO user;   #example of INSERT, UPDATE, DELETE etc.

GRANT admin TO alice;                                    #grant role to user
CREATE USER newuser WITH PASSWORD 'newpassword';         #create user
DROP USER charlie;                                       #delete user
ALTER USER postgress PASSWORD 'test123';                 #change password tp user

#check which users have replication privileges in PostgreSQL
SELECT usename FROM pg_user WHERE useconfig = 'true' AND usecreatedb = 'false' AND usesuper = 'false' AND userepl = 'true';

postgres in Docker






















