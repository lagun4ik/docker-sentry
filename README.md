# 👮 Sentry on Docker Compose

Easy way to bootstrap the Sentry docker infrastructure (with Postgres, Redis, RabbitMQ)

Just create env files and run one of the start commands!

## Сreate env files

```bash
cp ./env/postgres.env.exmple ./env/postgres.env
cp ./env/rabbitmq.env.exmple ./env/rabbitmq.env
cp ./env/sentry.env.exmple ./env/sentry.env
sed -i 's|SENTRY_SECRET_KEY=|SENTRY_SECRET_KEY='"$(docker run --rm sentry:8.18.0 config generate-secret-key)"'|g' ./env/sentry.env
```

## Start:

with nginx
```bash
docker-compose -f docker-compose.yml -f docker-compose.nginx.yml up -d
```

without nginx
```bash
docker-compose -f docker-compose.yml -f docker-compose.solo.yml up -d
```

### Default user

```
login: admin
pass: admin
```
