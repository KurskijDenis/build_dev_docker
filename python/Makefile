.PHONY: init_docker
init_docker:
	docker volume create $(PROJECT_NAME)_python_pkg_volume
	docker build -t $(PROJECT_NAME)_python_dev_3_12 .
	docker run -it --rm -v $(PROJECT_NAME)_python_pkg_volume:/python_pkg_volume --entrypoint pip $(PROJECT_NAME)_python_dev_3_12 install -t /python_pkg_volume python-lsp-server

.PHONY: pip_install_pkg 
pip_install_pkg:
	docker run -it --rm -v $(PROJECT_NAME)_python_pkg_volume:/python_pkg_volume --entrypoint pip $(PROJECT_NAME)_python_dev_3_12 install -t /python_pkg_volume $(PKG_NAME)

.PHONY: run 
run:
	docker run -it --rm -v $(PWD):/projects -v $(PROJECT_NAME)_python_pkg_volume:/python_pkg_volume --entrypoint python $(PROJECT_NAME)_python_dev_3_12 script.py
