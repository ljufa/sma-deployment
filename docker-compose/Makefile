TAG ?= latest
build_docker_local:
	../../top-tweets-backend/gradlew -p ../../top-tweets-backend clean build
	docker build ../../top-tweets-backend -t ljufa/top-tweets-backend:$(TAG)

	../../top-tweets-stream-collector/gradlew -p ../../top-tweets-stream-collector clean build
	docker build ../../top-tweets-stream-collector -t ljufa/top-tweets-stream-collector:$(TAG)

	../../top-tweets-web/gradlew -p ../../top-tweets-web clean build
	docker build ../../top-tweets-web -t ljufa/top-tweets-web:$(TAG)

redeploy_local: TAG:=$(shell uuidgen)
redeploy_local: build_docker_local
	TAG=$(TAG) docker-compose up -d

redeploy_from_docker_hub:
	docker-compose pull
	TAG=$(TAG) docker-compose up -d

log_backend:
	docker-compose logs -f --tail 200 top-tweets-backend
