# Usage

Create Docker volumes with the generated keys.

```
docker run -it \
    -v concourse-keys-web:/concourse-keys/web \
    -v concourse-keys-worker:/concourse-keys/worker \
    gangefors/concourse-keys
```

Use this volume when launching concourse.

**docker-compose.yml**
```
version: '3'

services:
[...]

  concourse-web:
    image: concourse/concourse
    command: web
    volumes: ["concourse-keys-web:/concourse-keys"]
[...]

  concourse-worker:
    image: concourse/concourse
    command: worker
    volumes: ["concourse-keys-worker:/concourse-keys"]
[...]
```
