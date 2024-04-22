.PHONY: tailwind-watch
tailwind-watch:
	../dependency/tailwindcss -i ./static/css/input.css -o ./static/css/style.css --watch

.PHONY: tailwind-build
tailwind-build:
	../dependency/tailwindcss -i ./static/css/input.css -o ./static/css/style.css --minify

.PHONY: templ-generate
templ-generate:
	templ generate

.PHONY: external-dependencies
external-dependencies:
	# For reference visit:
	wget https://github.com/tailwindlabs/tailwindcss/releases/download/v3.4.3/tailwindcss-linux-x64
	mv tailwindcss-linux-x64 tailwindcss
	mv tailwindcss ../dependency/
	chmod +x ../dependency/tailwindcss

.PHONY: go-dependencies
go-dependencies:
	go install github.com/cosmtrek/air@latest
	go install github.com/a-h/templ/cmd/templ@latest
	echo "installing go dependencies"



.PHONY: dev
dev:
	go build -o ./bin/$(APP_NAME)  ./cmd/$(APP_NAME)/main.go && air

.PHONY: build
build:
	make tailwind-build && make templ-generate && go build -o ./bin/$(APP_NAME) ./cmd/$(APP_NAME)/main.go