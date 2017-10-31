# gallery3-docker

It's a project to easily install gallery3 with mysql thanks docker

----------
## Setup ACR
`az acr create --name $AZURE_CONTAINER_REGISTRY_NAME --resource-group $MY_RESOURCE_GROUP --sku Basic --admin-enabled true`

## Build Docker Gallery3 image
`docker build --tag gallerydocker .'

## Tag Docker Gallery3 image
`docker tag gallerydocker $AZURE_CONTAINER_REGISTRY_NAME.azurecr.io/gallerydocker`

## Push the Gallery3 image to ACR
`docker login $AZURE_CONTAINER_REGISTRY_NAME.azurecr.io --username $AZURE_CONTAINER_REGISTRY_NAME --password $AZURE_CONTAINER_REGISTRY_PASSWORD`

`docker push $AZURE_CONTAINER_REGISTRY_NAME.azurecr.io/$DOCKER_IMAGE`

##Installation

At the first login, you need to pass the parametars to connect gallery3 to MySQL.
User, password, Hostname and port number (if needed).
