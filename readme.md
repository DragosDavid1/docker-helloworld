**Docker

1. Create a local folder in VCS (Virtual Code Studio)
2. Add the following files inside the folder: index.html, Dockerfile, runner.sh and nginx.conf
3. Create the Docker image running the below command: 
    docker build -t <image-name:version-number> --no-cache -f Dockerfile .
4. Push the image to the repositories (e.g - DockerHub):
    docker push <image-name:version-number>
5. Check the image size:
    docker image ls

**Kubernetes

1. Create a namespace
		###kubectl create ns <namespace-name> 
2. Apply kubernetes deployment mentioning the docker image previously created in the deployment.yaml file:
		kubectl create -f <deployment.yaml> 
3. Expose the service to a specific port: (e.g- port 32400)
		k expose deploy <deployment-name> -n <namepsace-name> --type=NodePort --overrides '{ "apiVersion": "v1","spec":{"ports": [{"port":80,"protocol":"TCP","targetPort":80,"nodePort":32400}]}}' 
4. Expose a service on a random port
		k expose deploy <deployment-name> -n <namepsace-name> --type=NodePort
