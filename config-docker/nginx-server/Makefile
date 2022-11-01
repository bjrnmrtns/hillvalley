build:
	docker build \
		-t nginx-server:latest \
		-f Dockerfile .

run:
	docker run \
		-p 8080:80 \
                -it --rm nginx-server:latest 

.PHONY: build
