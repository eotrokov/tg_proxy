# Telegram MTProto proxy

Контейнерный MTProto-прокси для нативных клиентов Telegram и небольшая веб-страница
с кнопкой подключения. HTTP-прокси Telegram-клиенты не поддерживают, поэтому
используется совместимый протокол MTProto.

## Запуск

```bash
cp .env.example .env
# Замените значение PROXY_SECRET на результат: openssl rand -hex 16
docker compose up -d
```

Прокси слушает TCP-порт `8443`, а веб-страница — `8081`.

Готовая ссылка для подключения:

```text
tg://proxy?server=SERVER_IP&port=8443&secret=PROXY_SECRET
```

Веб-странице можно передать её URL-кодированной строкой:

```text
http://SERVER_IP:8081/?link=tg%3A%2F%2Fproxy%3Fserver%3DSERVER_IP%26port%3D8443%26secret%3DPROXY_SECRET
```

`.env` содержит секрет доступа и намеренно не добавляется в репозиторий.
