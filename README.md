# Sentry on Docker Compose

Easy way to bootstrap the Sentry docker infrastructure (with Postgres, Redis, RabbitMQ)
Just run one of the start commands!

## Start:

with nginx
```
docker-compose -f docker-compose.yml -f docker-compose.nginx.yml up -d
```

without nginx
```
docker-compose -f docker-compose.yml -f docker-compose.solo.yml up -d
```

### Default user

```
login: admin
pass: admin
```