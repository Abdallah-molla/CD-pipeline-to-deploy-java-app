# simple-java-app
- This is simple Java App to Test Continous Deployment
 - Project-Overview Steps:
 * install 2 VM , one for Jenkins Server and other for node to run docker container on it during deployment
 * install jenkins on VM1 and setup second VM as a node in jenkins with "vm-agent" label and make sure that java 17 has been installed on agent
 * save dockerhub and github and jenkins agent credentials on jenkins server from manage jenkins then credentials then add them to use them during configuration pipeline
 * write docker file then write jenkins file to build docker file and push it to docker hub and then pull image from docker hub to run it on VM agent as a container
 * then you can check that the image already found on docker hub and make sure that the container already found on VM agent using docker ps command


