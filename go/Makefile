.PHONY: init_docker
init_docker:
	docker volume create $(PROJECT_NAME)_go_pkg_volume
	docker build -t $(PROJECT_NAME)_go_dev_1_22 .

.PHONY: go_download
go_download:
	docker run -it --rm -v $(PROJECT_NAME)_go_pkg_volume:/go_pkg_volume --entrypoint go $(PROJECT_NAME)_go_dev_1_22 mod download $(PKG_NAME)

.PHONY: go_get
go_get:
	docker run -it --rm -v $(PROJECT_NAME)_go_pkg_volume:/go_pkg_volume --entrypoint go $(PROJECT_NAME)_go_dev_1_22 get $(PKG_NAME)

.PHONY: build 
build:
	docker run -it --rm -v $(PWD):/projects -v $(PROJECT_NAME)_go_pkg_volume:/go_pkg_volume --entrypoint go $(PROJECT_NAME)_go_dev_1_22 build cmd/main.go 
