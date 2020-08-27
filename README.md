# Docker Compose for CORE Network

Docker-compose to easily build the Core Blockchain nodes - Boids.

## Variants

<dl>
<dt>docker-compose.yml</dt>
<dd>Installation of Mainnode Boid directly from the official image.</dd>
<dt>docker-compose-mainnet.yml</dt>
<dd>Build & Install the Mainnode Boid from Git repository.</dd>
<dt>docker-compose-devin.yml</dt>
<dd>Build & Install the Devin Testnet Boid from Git repository.</dd>
<dt>docker-compose-koliba.yml</dt>
<dd>Build & Install the Koliba Testnet Boid from Git repository.</dd>
</dl>

## Settings

### Arguments

* `NETWORK` network name to deploy
* `DATADIR` directory path to store Blockchain
* `EXPOSEPORTS` ports to be exposed inside the docker container

### Ports

Ports to be exposed outside of the Docker container.

* `8545:8545/tcp` HTTP-RPC (disabled)
* `8546:8546/tcp` WS (disabled)
* `8547:8547/tcp` GraphQL (disabled)
* `30300:30300/tcp` Peers (enabled)
* `30300:30300/udp` Peers (enabled)

## Usage

```sh
docker-compose -f docker-compose.yml up -d
```

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

## License

[Unlicense License](LICENSE)
