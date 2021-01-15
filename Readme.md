# Base crud spring mvc application

## Run 
```bash
	mvn spring-boot:run
```
or with wrapper 
```bash
	 ./mvnw spring-boot:run
```
## Default page 
```html
http://localhost:8000/swagger-ui.html
```

# Docker 
## Build image
Build image from docker file. Dot - get docker file from current directory 
```bash
  docker build -t spring-rest-h2-app:1.0.0 .
```

### Optional, check new image in list 
```bash
   docker images 
```

### Run in container 

#### Build and run 
```bash
   docker run -p 8001:8000 --name spring-h2-container spring-rest-h2-app:1.0.0
```

|   Description			| Value			   |
|---				|---			   |
|port on local machine   	| 8001  		   |	
|container port    		| 8000  		   |	
|image name 			| spring-rest-h2-app:1.0.0 |
|container name 	   	| spring-h2-container      |

#### Just run
```bash
   docker start spring-h2-container
```
------------------------------------------------------------------
## Dockerhub 
Login 
```bash
docker login 
```
### Docker commit 
docker commit [CONTAINER_NAME|CONTAINER_ID] [USER_PROFILE_NAME] 

``` bash
  docker commit spring-h2-container sevad/spring-h2-rest:v1.0.0
```
as a result we created image and we can push to docker hub 
```bash
  docker push  sevad/spring-h2-rest
```

### Options 
## Renamed image for docker hub 

docker tag [IMAGE_NAME] [DOCKER_HUB_PUBLIC_REPO_NAME][:version]

```bash
 docker tag sevad/spring-h2-rest sevad/springh2k8s:latest
```
push to exists docker repo 
```bash
   docker push  sevad/springh2k8s
```


## Run. g
situation when image doesn't exists in local machine 
```bash
    docker run -it  -p 18001:8000 \
          --name MY_SPRING_H2 \
          sevad/springh2k8s
```



