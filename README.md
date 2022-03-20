# Docker Compose for CORE Network

Docker-compose to easily build the Core Blockchain nodes — Boids.

## Variants

<dl>
<dt>docker-compose.yml</dt>
<dd>Installation of Mainnode Boid directly from the official image.</dd>
<dt>docker-compose-mainnet.yml</dt>
<dd>Build & Install the Mainnode Boid from Git repository.</dd>
<dt>docker-compose-devin.yml</dt>
<dd>Build & Install the Devin Testnet Boid from Git repository.</dd>
</dl>

## Settings

### Arguments

* `NETWORK` Network name to deploy
* `CHAINDIR` Directory path to store Blockchain data and node data
* `KEYDIR` Directory path to store keystore
* `SYNCMODE` Blockchain sync mode ("fast", "full", or "light") (default: "full")
* `GCMODE` Blockchain garbage collection mode ("full", "archive") (default: "full")
* `EXPOSEPORTS` Ports to be exposed inside the docker container

### Ports

Ports to be exposed outside of the Docker container.

* `8545:8545/tcp` HTTP-RPC (disabled)
* `8546:8546/tcp` WS (disabled)
* `8547:8547/tcp` GraphQL (disabled)
* `30300:30300/tcp` Peers (enabled)
* `30300:30300/udp` Peers (enabled)

## Volumes

Docker-compose is creating [Docker volume](https://docs.docker.com/storage/volumes), which is very useful for updating client without loosing Blockchain data.

We are creating volume: `/var/lib/core/{network name}` with mounting point `/core/{network name}`.

## Usage

```sh
docker-compose -f docker-compose.yml up -d
```

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

## License

[CORE License](LICENSE)
