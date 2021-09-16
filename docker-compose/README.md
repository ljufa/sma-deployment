- create data dir for kafka and zk
```bash
mkdir -p ./data/kfk
mkdir -p ./data/zk
chmod a+rwx -r ./data
```
- create `.env` file with twitter bearer token
```bash
TWITTER__AUTH_TOKEN=<paste your token here>
```

- run containers using docker hub repository
`TAG=latest docker-compose up -d`
  
- build and run local containers
`make redeploy`

- open `http://localhost:8080` in the browser