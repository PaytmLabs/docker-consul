AWS_REGION ?= us-west-2
ECR_REPO ?= 433726475936.dkr.ecr.us-west-2.amazonaws.com
IMAGE_NAME ?= consul
IMAGE_TAG ?= latest

build_push:
	$(SUDO) $$(aws ecr get-login --no-include-email --region us-west-2)
	$(SUDO) docker build -t consul . && $(SUDO) docker tag consul:$(IMAGE_TAG) $(ECR_REPO)/$(IMAGE_NAME):$(IMAGE_TAG)
	$(SUDO) docker push $(ECR_REPO)/$(IMAGE_NAME):$(IMAGE_TAG)
