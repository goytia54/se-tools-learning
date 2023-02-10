# Docker Compose Core Features

## Env Variables
* inside of docker container
```
  environment:
    - runtime_env=dev
    - region=us-east-1
```

## Build Arguments
* build tool versions
* example: aws region
```
  build:
    context: .
    args: 
      - region=us-east-1
```

## Mounting Volumes
* `source:target:access-mode`
```
  volumes:
    - ./mysql:/var/lib/mysql:rw
```
* `./` current dir
* `../` parent directory
* `/` absolute path

## Named Volumes
* when running docker compose up, will copy old data to need volumes
* With out named volumes, new volumes are always accumlating. 
```
  volumes:
    - ./mysql:/var/lib/mysql:rw
    - kineteco:/var/lib/mysqal
volumes:
  kineteco: 
```

## Exposing Ports
* Can expose multiple ports
```
[host port]:[container port]
[from]:[to]
```

```
  ports:
    - "81:80"
```

## Enforcing Start-up Order
```
services:
  scheduler:
    depends_on:
      - database
```
