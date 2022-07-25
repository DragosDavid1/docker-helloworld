Docker

1. Create a local folder in VCS (Virtual Code Studio)
2. Add the following files inside the folder: index.html, Dockerfile, runner.sh and nginx.conf
3. Create the Docker image running the below command
    docker build -t <image-name:version-number> --no-cache -f Dockerfile .
4. Push the image to the repositories (e.g - DockerHub):
    docker push <image-name:version-number>
5. Check the image size:
    docker image ls
