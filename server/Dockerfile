FROM ubuntu:latest
# COPY latest garnish-server binary
COPY --from=garnish/server:latest /app/garnish-server /garnish-server
# COPY the stores.yaml stores minifests dirs
COPY . /
# start up
CMD /garnish-server -address ':8080' -config-path ./
