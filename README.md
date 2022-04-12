# ods-docker-images
Create docker images needed in pipelines and publish them in Docker Hub.

# Modules
Every subfolder of the root project is a module that will generate X Docker images in [DockerHub](https://hub.docker.com/u/opendevstackorg)

# Versioning
Following the [Semantic Versioning](https://semver.org/). We have two options:
- Create a version of the entire project  / Tag the 'entire' project
- Create a version of a module / Tag 'only' a 'module'

# Publish images to DockerHub
Once a TAG is pushed, a [GitHub action](https://github.com/opendevstack/ods-docker-images/actions) is executed if the tag matches a regular expression:
- "v[0-9]+.[0-9]+.[0-9]+"  ==> this will __PUBLISH__ a new Docker image for all modules.
- "v[0-9]+.[0-9]+.[0-9]+-moduleName.*" ==> this will __PUBLISH__ a new Docker image for the "moduleName".

Examples:
  - v1.0.0 ==> this will __PUBLISH__ a new Docker image for all modules, with the tags: [v1.0.0, latest]
  - v1.0.0-python.1  ==> this will __PUBLISH__ a new Docker image for __"python"__ module, with the tags: [v0.0.0-python.1, latest]
  

# PR Pipeline
A PR pipeline (check) will only test the modules with files changes (test = build local docker images) 
