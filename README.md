# Usage

## Build

```bash
./mvnw package
```

## Run

```bash
docker-compose up -d
```

## Trigger

```bash
curl localhost/health
```

```bash
curl localhost/exceed-gc-limit
```

# Known issues
heapdumps are not written; permissions seem to be wrong (/tmp/heapdumps is owned by root:root)

Reason: we are missing
    https://github.com/gbtec-ag/biccloud-domain-service/blob/development/src/assembly/docker/Dockerfile#L20-L21

Solution:
    Drop buildpacks and use com.spotify:dockerfile-maven-plugin
