FROM ubuntu:latest
# COPY latest garnish-server binary
COPY --from=garnish/server:latest /app/garnish-server /bin/garnish-server
WORKDIR /opt/garnish
# COPY the stores.yaml stores minifests dirs
COPY ./stores /opt/garnish/stores
COPY ./stores.yaml /opt/garnish/
COPY ./manifests /opt/garnish/manifests

# start up
CMD garnish-server -address ':8080' -config-path ./
