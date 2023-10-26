TAG ?= latest

build-amd:
	@echo "building docker image"
	docker buildx build --platform linux/amd64 --push -t alecsavvy/go-hello-world:$(TAG) .

build-arm:
	@echo "building docker image"
	docker buildx build --platform linux/arm64 --push -t alecsavvy/go-hello-world:$(TAG) .

build: build-amd build-arm

run:
	docker run -p 3000:3000 alecsavvy/go-hello-world:$(TAG) -d
