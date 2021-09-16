TAG ?= latest
build_docker_local:
	../../top-tweets-backend/gradlew -p ../../top-tweets-backend clean build
	docker build ../../top-tweets-backend -t ljufa/top-tweets-backend:$(TAG)

	../../top-tweets-stream-collector/gradlew -p ../../top-tweets-stream-collector clean build
	docker build ../../top-tweets-stream-collector -t ljufa/top-tweets-stream-collector:$(TAG)

	../../top-tweets-web/gradlew -p ../../top-tweets-web clean build
	docker build ../../top-tweets-web -t ljufa/top-tweets-web:$(TAG)

redeploy: TAG:=$(shell uuidgen)
redeploy: build_docker_local
	TAG=$(TAG) docker-compose up -d

log_backend:
	docker-compose logs -f --tail 200 top-tweets-backend