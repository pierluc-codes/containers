namespace := pl-codes.io/containers
project := gocompiler
mkfile_path := $(abspath $(lastword $(MAKEFILE_LIST)))
project_dir := $(dir $(abspath $(firstword $(MAKEFILE_LIST))))

all:
	docker run -it --rm \
		-v "$(project_dir):/usr/local/src/$(project)" \
		--workdir "/usr/local/src/$(project)" \
		$(namespace)/$(project) \
		./compile

env:
	docker run -it --rm \
		-v "$(project_dir):/usr/local/src/$(project)" \
		--workdir "/usr/local/src/$(project)" \
		$(namespace)/$(project) \
		/bin/bash

container:
	docker build . --tag $(namespace)/$(project)

