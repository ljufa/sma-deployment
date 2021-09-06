- create data dir for kafka and zk
```bash
mkdir -p ./data/kfk
mkdir -p ./data/zk
chmod a+rwx -r ./data
```

- run containers
`docker-compose up -d`