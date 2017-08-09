# Usage

Create a Docker volume with the generated keys.

```
docker run -it -v concourse-keys:/concourse-keys gangefors/concourse-keys
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
    volumes: ["concourse-keys:/concourse-keys"]
[...]

  concourse-worker:
    image: concourse/concourse
    command: worker
    volumes: ["concourse-keys:/concourse-keys"]
[...]
```
