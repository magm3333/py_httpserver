# http-server 
### by magm

Sintáxis:

```
./httpServer
./httpServer host_to_bind:port path_to_serve
```

> Default: 
> `httpServer 0.0.0.0:8080 .

Build:

```
docker build -t http-server .
```

Build multiarch:

```
docker buildx create --driver-opt network=host --use --name multi-arch


docker buildx build --platform linux/amd64,linux/arm64,linux/arm/v7 -f ./Dockerfile --push -t magm3333/http-server:0.0.1 -t magm3333/http-server:latest .
```

Iniciar contenedor:

```
docker run -it --rm -p 8080:8080 magm3333/http-server:latest
```

Mapeo de ROOT PATH

```
docker run -it --rm -p 8080:8080 -v /path/to/serve:/www magm3333/http-server:latest
```