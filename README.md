# pulpocon
![PulpoCon](img/logoHoriz.svg)
Material para el taller de observabilidad en la PulpoCon 2023

## Contenido
* [Presentacion](https://github.com/marromang/pulpocon/docs/presentacion)
* [Fork del repo de la demo de otel](https://github.com/marromang/opentelemetry-demo)
* [Documentacion oficial demo open telemetry](https://opentelemetry.io/docs/demo/)
## Instrucciones
Las instrucciones originales las teneis en la [web](https://opentelemetry.io/docs/demo/docker-deployment/) de la demo de opentelemetry, os las resumo aqui

Docker

```
git clone https://github.com/marromang/opentelemetry-demo.git
cd opentelemetry-demo/
docker compose build
docker compose up --no-build
```

Para usuarios de Linux
Se ha reportado un bug en el que aparace el error

Para solucionarlo (al menos por ahora), hay que :
```
git clone clone https://github.com/open-telemetry/opentelemetry-demo.git
cd opentelemetry-demo/
```
Luego modificar el docker-compose.yml, copiando el de este mismo repo que está en la carpeta [config](https://github.com/marromang/pulpocon/config/docker-compose.yml)
Y ya, arrancamos
````
docker compose build
docker compose up --no-build
```

En todos los casos, los endpoins seran:
* Web store: http://localhost:8080/
* Grafana: http://localhost:8080/grafana/
* Feature Flags UI: http://localhost:8080/feature/
* Load Generator UI: http://localhost:8080/loadgen/
* Jaeger UI: http://localhost:8080/jaeger/ui/

![pulpito](img/pulpi.png)