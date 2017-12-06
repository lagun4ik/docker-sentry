# 👮 Sentry on Docker Compose

Easy way to bootstrap the Sentry docker infrastructure (with Postgres, Redis, RabbitMQ)

Just create env files and run one of the start commands!

## Create env files

```bash
cp ./env/postgres.env.example ./env/postgres.env
cp ./env/rabbitmq.env.example ./env/rabbitmq.env
cp ./env/sentry.env.example ./env/sentry.env
sed -i 's|SENTRY_SECRET_KEY=|SENTRY_SECRET_KEY='"$(docker run --rm sentry:8.22.0 config generate-secret-key)"'|g' ./env/sentry.env
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
