.PHONY: init_docker
init_docker:
	docker volume create $(PROJECT_NAME)_js_modules_volume
	docker build -t $(PROJECT_NAME)_js_node_22 .
