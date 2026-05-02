## Запуск

```
docker compose up -d --build
```

Для GPT-ассистента ключ должен быть в `/home/raim/raim/heart/.env`:

```
OPENAI_API_KEY=your-api-key
OPENAI_MODEL=gpt-4o-mini
```

## Сервисы

Grafana: http://localhost:3000
Prometheus: http://localhost:9090
Heart app: http://localhost:1111

## Метрики heart

```
curl http://localhost:1111/metrics
```
