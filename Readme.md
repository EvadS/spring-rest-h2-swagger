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
 ```bash
 docker build --file=Dockerfile \
      --tag=myk8sapp .
 ```

### Optional, check new image in list 
```bash
   docker images 
```

### Run in container 

#### Build and run 
```bash
	docker run -p 8001:8000 --name spring-h2-container myk8sapp

```

|   Description			| Value			|
|---				|---			|
|port on local machine   	| 8001  		|	
|container port    		| 8000  		|	
|image name 			| myk8sapp  		|
|container name 	   	| spring-h2-container   |

#### Just run
```bash
   docker start spring-h2-container
```

## Dockerhub 

Login 
```bash
docker login 
```
## Reaname image
```bash
 docker tag myk8sapp sevad/springh2k8s:latest
```

## Upload image
```bash
    docker push sevad/springh2k8s:latest
```

## Run. 
situation when image doesn't exists in local machine 
```bash
    docker run -it  -p 18001:8000 \
          --name MY_SPRING_H2 \
          sevad/springh2k8s
```



