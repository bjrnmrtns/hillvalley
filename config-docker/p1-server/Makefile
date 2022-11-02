build:
	docker build \
		-t p1-server:latest \
		-f Dockerfile .

run:
	docker run \
                -p 8086:8086 \
                -it --rm p1-server:latest 

.PHONY: build
