DOCKER_IMAGE_VERSION=1.4.12
DOCKER_IMAGE_NAME=artem236/rpi-mosquitto
DOCKER_IMAGE_TAGNAME=$(DOCKER_IMAGE_NAME):$(DOCKER_IMAGE_VERSION)

default: build

build:
	chmod +x docker-entrypoint.sh
	docker build -t $(DOCKER_IMAGE_TAGNAME) .
	docker tag $(DOCKER_IMAGE_TAGNAME) $(DOCKER_IMAGE_NAME):latest

push:
	docker push $(DOCKER_IMAGE_TAGNAME) 
	docker push $(DOCKER_IMAGE_NAME):latest

test:
	docker run --rm $(DOCKER_IMAGE_TAGNAME) /bin/echo "Success."

rmi:
	docker rmi -f $(DOCKER_IMAGE_TAGNAME)

rebuild: rmi build