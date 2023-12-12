## Project Skeleton

((docker-task for veroDigital))

|---- /mssql        
    
    |---- Dockerfile
    |---- entrypoint.sh
    |---- run-init.sh            
    |---- sql_init.sql
|---- /php       
    
    |---- 000-default.conf
    |---- Dockerfile  
    |---- QuickDbTest

|----docker-compose.yaml

## Steps to Solution

- Step 1: Install docker and docker-compose and other dependencies

- Step 2: Prepare Dockerfiles for images

- Step 3: Configure inside of Dockerfile for Permissons

- Step 4: Set the script and sql file so that the container is started and the database is ready when it is started.

- Step 5: Prepare docker-compose to launch containers 

- Step 6: Lets see the connection is successful.