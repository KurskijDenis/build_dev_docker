.PHONY: init_docker
init_docker:
	docker volume create $(PROJECT_NAME)_cpp_thirdparty_volume
	docker build -t $(PROJECT_NAME)_cpp_dev_clang_17 .

.PHONY: debug_generate
debug_generate:
	docker run -it --rm --entrypoint cmake \
		-v $(PWD):/projects \
		-v $(PROJECT_NAME)_cpp_thirdparty_volume:/thirdparty \
		$(PROJECT_NAME)_cpp_dev_clang_17\
		-B build/Debug \
		-S . \
		-DCMAKE_BUILD_TYPE=Debug \
		-DCMAKE_EXPORT_COMPILE_COMMANDS=1

.PHONY: debug_build
debug_build:
	docker run -it --rm --entrypoint cmake \
		-v $(PWD):/projects \
		-v $(PROJECT_NAME)_cpp_thirdparty_volume:/thirdparty \
		$(PROJECT_NAME)_cpp_dev_clang_17 \
		--build build/Debug \
		-j 8
# 		--verbose
