.PHONY: all build test-all test lint vet

all: test-all build

build:
	docker build --no-cache -t kirillborisov89/k8s-deployment-strategies:v2.0.0 .

test-all: vet lint test

test:
	go test -v -parallel=4 ./...

lint:
	@go get github.com/golang/lint/golint
	go list ./... | xargs -n1 golint

vet:
	go vet ./...
