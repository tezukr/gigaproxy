# GIGAPROXY - proxy image which allows you to debug and test TEZOS API requests, without the need to install a tezos arhive  node

## Benefits:
	- no need to install an archive node (https://mainnet.tezos.org.ua used as default)
	- custom logs for debugging and testing
	- log files can be used for further analysis / statistics
	- it can easily be configured for a separate endpoint - on your own node or any other
	- lightweight nginx proxy

## Install docker-compose

	$ sudo curl -L "https://github.com/docker/compose/releases/download/1.25.3/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

	$ sudo chmod +x /usr/local/bin/docker-compose

## Clone repo

### Use Makefile to start, stop, build, attach docker image

### To build and start image:
	$ make build

## To stop image:
	$ make stop

## To start image:
	$ make start

## To attach image:
	$ make attach
	
## To check status:
	$ make status

### Logs
Logs located in ./logs/nginx catalog:
	
	giga.proxy_access.log (access log)  
	giga.proxy_error.log (error log)

Log format definition for debugging/testing purposes:

log_format upstr '$host "$time_local" $status $request_time $upstream_response_time $request_length $bytes_sent $remote_addr->$upstream_addr $request';

# Usage: 
	$ curl localhost:8080/chains/main/blocks/head/context/contracts/tz1RaQMyWSExjoykpbA9Ga241WeMEGutXqLF

# Log example:

mainnet.tezos.org.ua "19/Feb/2020:11:46:46 +0100" 200 0.100 0.100 - 152 444 109.252.2.236->94.130.161.135:8732 GET /chains/main/blocks/807107/context/contracts/tz1RWg4v4qwi3p1XjTxQ7gYRyQD7qPUZuaR7 HTTP/1.1
