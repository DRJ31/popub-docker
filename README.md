# Popub Docker

## Popub Relay

### Installation
You can obtain it via:
```bash
docker pull dengrenjie31/popub-relay
```
If you want to build it by yourself, you should first run:
```bash
docker pull ubuntu
```
Then go to `popub-relay` diretory and
```bash
docker build -t popub-relay .
```

### Usage
```
docker run -d \
 --name=popub-relay \
 --restart=always \
 -p <Receive Port>:<Receive Port> \
 -p <Exposed Port>:<Exposed Port> \
 dengrenjie31/popub-relay :<Receive Port> :<Exposed Port> <Password>
```

### Parameters
* `--name=popub-relay` You can use whatever name you want
* `<Receive Port>` The port to receive data from local device
* `<Exposed Port>` The port you use to access reversed proxy

## Popub Local

### Installation
You can obtain it via:
```bash
docker pull dengrenjie31/popub-local
```
If you want to build it by yourself, you should first run:
```bash
docker pull ubuntu
```
Then go to `popub-local` diretory and
```bash
docker build -t popub-local .
```

### Usage
```
docker run -d \
 --name=popub-local \
 --restart=always \
 dengrenjie31/popub-local <Local IP>:<Local Port> <Remote IP>:<Remote Port> <Password>
```

### Parameters
* `--name=popub-local` You can use whatever name you want
* `<Local IP>` Obtain it by `ip addr show docker0` and use the IPv4 address after `inet`
* `<Local Port>` Local port you want to expose to remote machine which has a public network IP
* `<Remote IP>` Remote machine which has a public network IP.
* `<Remote Port>` A port in remote machine to receive data sent from the local machine.

