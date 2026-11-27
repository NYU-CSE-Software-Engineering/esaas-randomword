# To build and run this application using Docker:
1. `docker build -t esaas-randomword` This will build a Docker image for this application based on Ruby 4.0.10, and assigns
the image name of `esaas-randomword`. Following this command, you should see the image in the Docker Desktop application. Note that
it is not yet a running container.

2. `docker run -d -p 3000:9292 --name randomword-app esaas-randomword`. This will run the specified image (`esaas-randomword`) with
the following options:
  * `-d`: Runs the container in detached mode (in the background), freeing up your terminal so you can run subsequent commands. (Omit `-d` if you want to watch the live server logs in your terminal, though you will need to open a second terminal tab to run the shell command below).
  * `-p 3000:9292`: Maps external host port 3000 to internal container port 9292 (matching the `EXPOSE 9292` and rackup `-p 9292` configuration in your Dockerfile).
  * `--name randomword-app`: Assigns a predictable name to the running container so you don't have to look up a randomly generated container ID later.

3. If you wish to open and use a shell that is running inside the Docker container, use the following command:
`docker exec -it randomword-app /bin/bash`.
