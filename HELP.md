### Create self signed certificate for local usage (windows)
```bash
    cp docker/nginx/cert
    openssl req -x509 -newkey rsa:4096 -keyout key.pem -out cert.pem -days 365 -nodes -subj "/CN=u.rl"
```

### Docker compose up
It will create the network, start the `mysql`, `app` and `nginx` containers.
```bash
docker-compose down && docker-compose up --build
```

### Check if nginx is running
```http request
GET http://localhost/healthz
```

By default, the browser sends the request on port 443 using HTTPS.
If you want to access only port 80 locally, you need to explicitly specify to use HTTP: http://localhost/healthz
