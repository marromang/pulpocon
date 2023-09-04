# pulpocon
![PulpoCon](img/logoHoriz.svg)
Material para el taller de observabilidad en la PulpoCon 2023

## Contenido
* [Presentacion](https://github.com/marromang/pulpocon/docs/presentacion)
* [docker-compose modificado](https://github.com/marromang/pulpocon/config/docker-compose.yml)

## Instrucciones
las instrucciones originales las teneis en la web de la demo de opentelemetry, os las resumo aqui

Docker

```
git clone https://github.com/open-telemetry/opentelemetry-demo.git
cd opentelemetry-demo/
docker compose build
docker compose up --no-build
```

Kubernetes
```
helm repo add open-telemetry https://open-telemetry.github.io/opentelemetry-helm-charts
helm install my-otel-demo open-telemetry/opentelemetry-demo
```
o
```
kubectl create namespace otel-demo
kubectl apply --namespace otel-demo -f https://raw.githubusercontent.com/open-telemetry/opentelemetry-demo/main/kubernetes/opentelemetry-demo.yaml
```

Port forwarding
```
kubectl port-forward svc/my-otel-demo-frontendproxy 8080:8080
kubectl port-forward svc/my-otel-demo-otelcol 4318:4318
```

En todos los casos, los endpoins seran:
* Web store: http://localhost:8080/
* Grafana: http://localhost:8080/grafana/
* Feature Flags UI: http://localhost:8080/feature/
* Load Generator UI: http://localhost:8080/loadgen/
* Jaeger UI: http://localhost:8080/jaeger/ui/

### Notas
En el caso de mi Apple Silicon tuve que modificar ciertas versiones y perámetros en el docker-compose, en caso de que os haga falta, lo tenéis [aqui](https://github.com/marromang/pulpocon/config/docker-compose.yml).

![pulpito](img/pulpi.png)