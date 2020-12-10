### Alpine Docker containers for Elixir
A single CI pipeline to build Erlang / Elixir / Phoenix Docker containers.



### Usage
All relevant information is kept in a single file: `bin/env-vars`.

Following ENV variables are available:

```
export REFRESHED_AT="2020-12-10"
export DOCKERHUB_USER="mindreframer"

export ALPINE_VERSION="3.12.1"

export ERLANG_VERSION="23.1.2"
export ERLANG_IMAGE="alpine-erlang"

export ELIXIR_VERSION="1.11.1"
export ELIXIR_IMAGE="alpine-elixir"
```

### Opt-in for container building
To prevent waiting for all containers on all commits, following magic strings are used in commit messages:
- `[skip ci]`
- `[with-erlang]` - include the Erlang container
- `[with-elixir]` - include the Elixir container
- `[with-phoenix]` - include the Phoenix container

To trigger building all 3 containers, use `[with-erlang, with-elixir, with-phoenix]`.


### Secrets
Github Actions depend on following secrets being available:
- `DOCKERHUB_USER`
- `DOCKERHUB_TOKEN`
