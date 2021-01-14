# deploy_simple_app
Simple application deploy (docker-compose, portainer, swarm)
You need: Docker Swarm and portainter 

1. Create images:
	sudo docker-compose -f docker-compose.yml build
	
2. Check
	sudo docker images

3. Create repo on DockerHub and remember accaunt-name/reposit_name (kvadevops/deploy-app)

4. Change image name and tag
	sudo docker tag myapp-image1:nginx kvadevops/deploy-app:nginx
	sudo docker tag myapp-image2:php kvadevops/deploy-app:php

5. Load image to DockerHub
	sudo docker login
 	sudo push kvadevops/deploy:nginx
 	sudo push kvadevops/deploy:php

6. Go to Portainer 
	New stack > enter command:
===========================================				
version: "3"
services:
  nginx: 
    image: kvadevops/deploy-app:nginx
    ports:
      - 80:80
  php:
    image: kvadevops/deploy-app:php
===========================================

6.1 If your repo private - change in portainer > Registers

7. Check our app in browser
	
