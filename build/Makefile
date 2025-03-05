# 定义镜像名称和标签
IMAGE_REGISTRY = crpi-vky0opaxai0svu2g.cn-chengdu.personal.cr.aliyuncs.com/bodwang/
IMAGE_BACK = $(IMAGE_REGISTRY)taiga-back
IMAGE_FRONT = $(IMAGE_REGISTRY)taiga-front
TAG = 250305

# 默认目标
all: build-back build-front

# 构建 taiga-back 镜像
build-back:
	docker build -t $(IMAGE_BACK):$(TAG) -f Dockerfile.taiga-back .
	docker tag $(IMAGE_BACK):$(TAG) $(IMAGE_BACK):latest

# 构建 taiga-front 镜像
build-front:
	docker build -t $(IMAGE_FRONT):$(TAG) -f Dockerfile.taiga-front .
	docker tag $(IMAGE_FRONT):$(TAG) $(IMAGE_FRONT):latest

# 上传镜像
push-back:
	docker push $(IMAGE_BACK):$(TAG)
	docker push $(IMAGE_BACK):latest

# 上传镜像
push-front:
	docker push $(IMAGE_FRONT):$(TAG)
	docker push $(IMAGE_FRONT):latest

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
