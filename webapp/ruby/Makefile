.DEFAULT_GOAL := help

kataribe: ## Start Puma
	@sudo cat /var/log/nginx/access.log | kataribe
	@echo 'Kataribe!'

puma-start: ## Start Puma
	@sudo bundle exec pumactl start
	@echo 'Started Puma'

puma-restart: ## Restart Puma
	@sudo bundle exec pumactl restart
	@echo 'Restarted Puma'

puma-stop: ## Stop Puma
	@sudo bundle exec pumactl stop
	@echo 'Stopped Puma'

nginx-start: ## Start Nginx
	@sudo service nginx start
	@echo 'Started Nginx'

nginx-restart: ## Restart Nginx
	@sudo service nginx -s reload
	@echo 'Restarted Nginx'

nginx-stop: ## Stop Nginx
	@sudo service nginx -s stop
	@echo 'Stopped Nginx'

h2o-start: ## Start H2O
	@sudo systemctl start h2o
	@echo 'Started H2O'

h2o-restart: ## Restart H2O
	@sudo systemctl restart h2o
	@echo 'Restarted H2O'

h2o-stop: ## Stop H2O
	@sudo systemctl stop h2o
	@echo 'Stopped H2O'

redis-start: ## Start Redis
	@sudo systemctl start redis-server
	@echo 'Started redis-server'

redis-restart: ## Restart Redis
	@sudo systemctl restart redis-server
	@echo 'Restarted redis-server'

redis-stop: ## Stop Redis
	@sudo systemctl stop redis-server
	@echo 'Stopped redis-server'

.PHONY: help
help:
    @grep -E '^[a-z0-9A-Z_-]+:.*?## .*$$' $(MAKEFILE_LIST) | sort | awk 'BEGIN {FS = ":.*?## "}; {printf "\033[36m%-30s\033[0m %s\n", $$1, $$2}'
