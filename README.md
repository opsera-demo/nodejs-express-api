# nodejs-express-api
This repo contains a demo API that will allow opsera to perform build, test, security, and deployment functionality for Opsera customers.

### Build Commands
`npm install` - This will build all nodejs dependencies into the `node_modules` directory. _The project will not function correctly without this command being run. The `node_modules` directory is part of the `.gitignore` file and should not be committed to SCM.

`docker build -t <tag> .` - This will build the docker container and tag it with a custom string. You can then push this tagged container image to an artifact repository like Artifactory, Nexus, or Amazon/Azure Container Registries. The dot at the end of the command will provide an argument that will look for a `Dockerfile` in the directory the command is run from.  If you provide the `-f <path_to_Dockerifle>` flag then you can specify a `Dockerfile` of your chooosing.

### Run Commands
`docker run -p <port>:<port> <tag>` - The first `port` argument is the port that will be exposed on the HOST machine. The second `port` argument is the port that will be exposed from inside the docker container. The `tag` argument will choose the image that you want to run.
Example: `docker run -p 80:3000 my-docker-container` will expose the container port 3000 to port 80 on the host machine running the my-docker-container image.  In order to access this particular run command from a browser you would go to `<host_ip_or_dns_address>:80` to interact with the application.

### Test Commands
`npm run test` - This command will run an API confirmation test that will interact with the enclosed API at the provided `HOST_PORT`. The default PORT it will target is port `3000`.