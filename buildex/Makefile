default: build manifest run

build-amd:
	@echo "building docker image"
	docker buildx build --platform linux/amd64 --push -t alecsavvy/go-hello-world:latest .

build-arm:
	@echo "building docker image"
	docker buildx build --platform linux/arm64 --push -t alecsavvy/go-hello-world:latest-arm .

build: build-amd build-arm

manifest:
	docker buildx imagetools create -t alecsavvy/go-hello-world:latest \
		alecsavvy/go-hello-world:latest \
    	alecsavvy/go-hello-world:latest-arm

run:
	docker run -p 3000:3000 alecsavvy/go-hello-world:latest -d
