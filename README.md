## Work-in-progress

### manual run

```bash
docker pull prom/prometheus

docker pull grafana/grafana

touch prometheus.yml

docker run -it -d --name prometheus -p 9090:9090 -v ./:/etc/prometheus prom/prometheus -config.file=/etc/prometheus/prometheus.yml

```

### simple run

```bash
docker run --name prometheus -p 127.0.0.1:9090:9090 prom/prometheus

```

### compose everything

```sh
docker-compose up
```

Install wmi exporter
[wmi exporter] https://github.com/martinlindhe/wmi_exporter


Prometheus - show configured targets 

http://localhost:9090/targets


Grafana

http://localhost:3000
Grafana add data source to `prom:9090`


