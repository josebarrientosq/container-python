# Container python

## Container local

### Build the image
```
docker build --tag=hello-python
```
### to list the image
 
```
docker image ls
```
 
### Run the container from the image and execute the app
```
docker run -it hello-python python app.py --name "Big John"
# output "Big John"
````

### To see the container
```
docker ps -a
```

## Push the container to AWS ECR
![ecr](https://user-images.githubusercontent.com/35469345/135733332-f4aaee57-da1c-4441-a9a7-560612f6999d.jpg)

### Create a repository in ECR and view the push command
```
aws ecr get-login-password --region us-east-2 | docker login --username xxx --password-stdin xxxx
```
### Build the image if it does not exist
 ```
 docker build -t hello-python .
 
 ```
 ### Tags the image
 ```
 docker tag hellopython:latest xxxxxx.dkr.ecr.us-east-2.amazonaws.com/hellopython:latest
 ```
 ### Push the image
 ```
 docker push xxxxx.dkr.ecr.us-east-2.amazonaws.com/hellopython:latest
 ```
 
 ## Pulling the image
 ### In another instance cloud9 copy the credentials and pull the image
 ```
 aws ecr get-login-password --region us-east-2 | docker login --username xxx --password-stdin xxxx
 docker push xxxxx.dkr.ecr.us-east-2.amazonaws.com/hellopython:latest
 ```
