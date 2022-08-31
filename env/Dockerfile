FROM ubuntu:latest
COPY --from=garnish/kimono:latest /kimono /kimono
ENTRYPOINT /kimono -manifest env -address http://server:8080 
CMD env
