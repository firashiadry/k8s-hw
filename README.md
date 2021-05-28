# PetClinic-Kubrnates
-------------------------------------------------------------------------------------------------


## how to run your project:
1- Use git to clone down the Spring Pet Clinic git repo locally:
```sh
git clone https://github.com/spring-projects/spring-petclinic.git
```
2- Build a Docker image for Spring Pet Clinic:
```sh
mvn compile -Dimage=spring/petclinic:spring-k8s-1 com.google.cloud.tools:jib-maven-plugin:1.0.0:dockerBuild
```

3- Validate the Docker Image works locally : docker run -ti --rm -p 8080:8080 paulczar/petclinic:spring-k8s-1 ------> localhost:8080

4- Run Pet Clinic in Kubernetes:
```sh
 kubectl apply -f deployment-service.yml
```
5- Access the petclinic app just like pointing your browser at localhost:8080
```sh
   kubectl port-forward deployment/springpetclinic-k8s 8080:8080
```



