# markdownApp
Another attempt at making markdown app with gotth stack (Go, Tailwind, Templ, HTMX) and Postgres


# Tech Stack
For reference on the original tech stack see: https://github.com/TomDoesTech/GOTTH

## Makefile
This Makefile is designed to simplify common development tasks for your project. It includes targets for building your Go application, watching and building Tailwind CSS, generating templates, and running your development server using Air.

### Targets:
```bash
make tailwind-watch
```
This target watches the ./static/css/input.css file and automatically rebuilds the Tailwind CSS styles whenever changes are detected.

```
make tailwind-build
```
This target minifies the Tailwind CSS styles by running the tailwindcss command.

```
make templ-generate
```
This target generates templates using the templ command.


```
make dev
```
This target runs the development server using Air, which helps in hot-reloading your Go application during development.

```
make build
```
This target orchestrates the building process by executing the tailwind-build, templ-generate, and go build commands sequentially. It creates the binary output in the ./bin/ directory.

