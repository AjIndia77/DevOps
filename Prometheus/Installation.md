First, create a dedicated Linux user for Prometheus and download Prometheus:
```sh
sudo useradd --system --no-create-home --shell /bin/false Prometheus
```