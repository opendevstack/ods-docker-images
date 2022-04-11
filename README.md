# ods-docker-images
Create docker images needed in pipelines and publish them in Docker Hub.

# Publish Docker imager to DockerHub
Once a PR is merged into __main__ branch, a [GitHub action](https://github.com/opendevstack/ods-docker-images/actions)  executed in __main__  that will:
- Publish a Docker image in [DockerHub](https://hub.docker.com/u/opendevstackorg) for every docker image changed by the PR
- For every published image, it will generate a "latest" and "sha commit" tag in DockerHub. We use [Unique tags strategy](https://docs.microsoft.com/en-us/azure/container-registry/container-registry-image-tag-version#unique-tags)






