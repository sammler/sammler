
## Structure

To make it simpler to work with multiple projects and services, they typically (if using the node.js/express stack) share the 
same folder structure:

```sh

| [root]
|── docs                    // document for the project
|── src
    |── config              // configuration files
    |── modules             // different express modules
    | app-server.js         // root for the express app
    | index.js
|── test                    // all tests
    |── unit
    |── component
    |── integration
    |── lib
| Dockerfile
| docker-compose.dev.yml
| docker-compose.yml
| package.json
| .verb.md
| .editorconfig
| .gitignore

```


## Scripts & Tooling

These are common scripts which should be implemented across all services:

Creating/updating documentation:

- `docs`
- `docs-if-necessary`

Building the default docker image:

- `d-build` - Build the Docker container as defined in `Dockerfile`.
- `d-run` - Run the Docker container as just previously build with `d-build`.

Setting up the docker environment:

- `dc-up` - Just a shortcut to `docker-compose up`.
- `dc-down` - Just a shortcut to `docker-compose down`.
- `dc-up:dev` - `docker-compose up` for the development environment.
- `dc-up:dev-b` - `docker-compose up` for the development environment, but using the `--build` option.
- `dc-down:dev` - `docker-compose down for the development environment.

Linting the project:

- `lint` - Run linter for both src and test.
- `lint:src` - Run the linter for the src dir.
- `lint:src:fix` - Run the linter in fix mode for the src dir.
- `lint:test` - Run the linter for the test dir.
- `lint:test:fix` - Run the linter in fix mode for the test dir.

Git hooks:
- `precommit`
- `prepublish`

### Tooling

Tools I use:

**husky**

**[github-changelog-generator](https://github.com/skywinder/Github-Changelog-Generator)**

 