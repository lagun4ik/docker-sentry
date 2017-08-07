## Start:

with nginx
```
docker-compose -f docker-compose.yml -f docker-compose.nginx.yml up -d
```

without nginx
```
docker-compose -f docker-compose.yml -f docker-compose.solo.yml up -d
```