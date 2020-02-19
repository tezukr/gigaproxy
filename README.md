# GIGAPROXY

Install docker-compose

sudo curl -L "https://github.com/docker/compose/releases/download/1.25.3/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose


Use Makefile to start, stop, build, attach docker image.

Example:
	$make build
	$make start
