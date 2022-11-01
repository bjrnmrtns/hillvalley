build: output/fs/home/git/.ssh/authorized_keys
	docker build \
		-t git-server:latest \
		-f Dockerfile .

run:
	docker run \
		-p 2222:22 \
                -v /home/$(USER)/repos:/srv/git/ \
                -it --rm git-server:latest

output/fs/home/git/.ssh/authorized_keys: /home/${USER}/.ssh/id_ed25519.pub
	mkdir -p output/fs/home/git/.ssh/
	cat /home/${USER}/.ssh/id_ed25519.pub > output/fs/home/git/.ssh/authorized_keys

clean:
	rm -r output

.PHONY: build
