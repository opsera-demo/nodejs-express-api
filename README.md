# nodejs-express-api
This repo contains a demo API that will allow opsera to perform build, test, security, and deployment functionality for Opsera customers.

### Build Commands
`npm install` - This will build all nodejs dependencies into the `node_modules` directory. _The project will not function correctly without this command being run. The `node_modules` directory is part of the `.gitignore` file and should not be committed to SCM.

`docker build -t <tag>` - This will build the docker container and tag it with a custom string. You can then push this tagged container image to an artifact repository like Artifactory, Nexus, or Amazon/Azure Container Registries.