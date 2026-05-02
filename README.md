## Запуск

```
docker compose up -d --build
```

## Сервисы

Grafana: http://localhost:3000
Prometheus: http://localhost:9090
Heart app: http://localhost:1111

## Метрики heart

```
curl http://localhost:1111/metrics
```
