### Deploying a Spring Boot application to a local Kubernetes 

### Commands to Run 
`mvn clean package`

`docker build -t spring-boot-app .`
`docker run -d -p 5000:5000 --restart=always --name registry registry:2`
`mvn package`
`docker build -t spring-boot-app .`
`docker tag spring-boot-app localhost:5000/spring-boot-app`
`docker push localhost:5000/spring-boot-app`
`kubectl apply -f deployment.yml`
#### Test if application is deployed succesfully
`curl -v http://localhost:31000/api/messages`
