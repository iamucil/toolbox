PHP_MIGRATOR_IMAGE ?= larevel-migration 
NODE_IMAGE ?= node:16-alpine

.PHONY: migrate deps-install

migrate: 
	@echo "running migrate"
	@docker build -t $(PHP_MIGRATOR_IMAGE) -f $(CURDIR)/php/Dockerfile . > /dev/null
	@echo "running laravel migrations"
	@docker run --rm -i \
		-v $(CURDIR)/app/web:/app \
		--workdir=/app \
		$(PHP_MIGRATOR_IMAGE) /bin/sh -c "php artisan migrate"

deps-install:
	@echo "running npm install"
	@docker run --rm -i -t \
		-v $(CURDIR)/app/web:/app \
		--workdir=/app \
		$(NODE_IMAGE) /bin/sh -c "npm install && npm run dev"