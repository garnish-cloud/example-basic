# Garnish + Kimono basic example
## a simple garnish server w/ kimono agent to control the container entrypoint's environment variables
### clone this repo and...
```
docker compose up env

example-basic-env-1  | time="2022-08-31 01:01:49" level=warning msg="Using ENV for address"
example-basic-env-1  | time="2022-08-31 01:01:49" level=warning msg="Using ENV for debug"
example-basic-env-1  | time="2022-08-31 01:01:49" level=warning msg="Using ENV for manifest"
example-basic-env-1  | KIMONO_ID=bdf2d6eb-3286-45bd-98a2-612f2ce25649
example-basic-env-1  | HOSTNAME=8918dbaea5b8
example-basic-env-1  | HOME=/root
example-basic-env-1  | PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
example-basic-env-1  | PWD=/
example-basic-env-1  | HELLO=world!
example-basic-env-1 exited with code 0
```

### garnish server configuration
#### manifests/env.yaml
```
# each manifest file can be called by the kimono agent
# this file configuresthe environment variables using the env store
env:
  passall: true
  src:
  - store: env
    paths: 
      - default
```
#### stores.yaml
```
# the stores.yaml configures various directories for use by manifests
env:
    driver: file
    driveropts:
        Parser: yaml
        Path: ./stores/envs
        Suffix: .yaml
```
#### stores/default.yaml
```
# this yaml map defines entrypoint environment variables when used in a manifest file
HELLO: world!
```