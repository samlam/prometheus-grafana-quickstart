# Work-in-progress

## manual run

```bash
docker pull prom/prometheus

docker pull grafana/grafana

touch prometheus.yml

docker run -it -d --name prometheus -p 9090:9090 -v ./:/etc/prometheus prom/prometheus -config.file=/etc/prometheus/prometheus.yml

```

## simple run

```bash
docker run --name prometheus -p 127.0.0.1:9090:9090 prom/prometheus

```

## compose everything

```sh
docker-compose up -d
```

Install wmi exporter
[wmi exporter] https://github.com/martinlindhe/wmi_exporter

Prometheus - show configured targets

http://localhost:9090/targets

Grafana

http://localhost:3000
Grafana add data source to `prom:9090`

## host.docker.internal

if for whatever reason, the internal host failed try adding the extra_host param (in docker-compose), here's how to lookup the ip

```sh
$ docker run --rm alpine ping -c 5 host.docker.internal
PING host.docker.internal (192.168.65.2): 56 data bytes
64 bytes from 192.168.65.2: seq=0 ttl=37 time=0.696 ms
64 bytes from 192.168.65.2: seq=1 ttl=37 time=0.698 ms
64 bytes from 192.168.65.2: seq=2 ttl=37 time=2.206 ms
64 bytes from 192.168.65.2: seq=3 ttl=37 time=1.067 ms
64 bytes from 192.168.65.2: seq=4 ttl=37 time=2.366 ms
```

