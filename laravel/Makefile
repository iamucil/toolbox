PHP_MIGRATOR_IMAGE ?= larevel-migration 
NODE_IMAGE ?= node:16-alpine
COMPOSER_IMAGE ?= composer:latest

.PHONY: init run deps-install

init:
	@echo "initializing laravel-app"
	@docker run --rm -i -t \
		-v $(CURDIR)/app:/app \
		--workdir=/app \
		$(COMPOSER_IMAGE) /bin/sh -c "composer create-project laravel/laravel web" 
	@mkdir -p $(CURDIR)/var/mariadb/data

run:
	@echo "running all services..."
	@docker-compose up --build --abort-on-container-exit --remove-orphans
	
deps-install:
	@echo "running npm install"
	@docker run --rm -i -t \
		-v $(CURDIR)/app/web:/app \
		--workdir=/app \
		$(NODE_IMAGE) /bin/sh -c "npm install && npm run dev"