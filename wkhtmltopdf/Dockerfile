FROM quantor/alpine-elixir-phoenix:1.13.3

# Important!  Update this no-op ENV variable when this Dockerfile
# is updated with the current date. It will force refresh of all
# of the base images and things like `apt-get update` won't be using
# old cached versions when the Dockerfile is built.
ENV REFRESHED_AT=2022-07-17

# Install NPM
RUN \
    mkdir -p /opt/app && \
    chmod -R 777 /opt/app && \
    apk update && \
    apk --no-cache --update add \
      wkhtmltopdf && \
    update-ca-certificates --fresh && \
    rm -rf /var/cache/apk/*

# Ensure latest versions of Hex/Rebar are installed on build
ONBUILD RUN mix do local.hex --force, local.rebar --force

WORKDIR /opt/app

CMD ["/bin/sh"]
