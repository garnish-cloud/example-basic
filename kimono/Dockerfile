FROM ubuntu:latest
COPY --from=garnish/kimono:latest /kimono /kimono
ENTRYPOINT /kimono -manifest test -address http://server:8080 -debug env
