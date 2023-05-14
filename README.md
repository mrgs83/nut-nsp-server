# nut-server
nut server docker image for serving switch nsp and xci to tinfoil on local network

## Quick Start

Pull latest build from docker hub

```
docker pull mrgs83/nut-nsp-server
````

Launch the nut-nsp-server docker container with the following command:

``` 
docker run -d \
    --name=nut-nsp-server \
    -p 9000:9000 \
    -v $GAMES:/games:rw \
    -e ID=$ID \
    -e PASSWORD=$PASSWORD \
    mrgs83/nut-nsp-server
```

Where:

- $GAMES : Path to switch NSP and XCI library on host.
- $ID : user id to use for credentials
- $PASSWORD : user password to use for credentials

## BUGS

- cron task to scan games need one minute to be first launched (due to the fact that I launch cron task before nut server, Docker specificity here :/)
- logs are not populated

## TODO

- Add env variables for port 
