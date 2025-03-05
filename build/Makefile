# 定义镜像名称和标签
IMAGE_BACK = my-custom-taiga-back
IMAGE_FRONT = my-custom-taiga-front
TAG = 250305

# 默认目标
all: build-back build-front

# 构建 taiga-back 镜像
build-back:
	docker build -t $(IMAGE_BACK):$(TAG) -f Dockerfile.taiga-back .

# 构建 taiga-front 镜像
build-front:
	docker build -t $(IMAGE_FRONT):$(TAG) -f Dockerfile.taiga-front .

# 清理构建的镜像
clean:
	docker rmi $(IMAGE_BACK):$(TAG) $(IMAGE_FRONT):$(TAG)

# 显示帮助信息
help:
	@echo "Usage: make [target]"
	@echo ""
	@echo "Targets:"
	@echo "  all          Build both taiga-back and taiga-front images (default)"
	@echo "  build-back   Build the taiga-back image"
	@echo "  build-front  Build the taiga-front image"
	@echo "  clean        Remove the built images"
	@echo "  help         Show this help message"
