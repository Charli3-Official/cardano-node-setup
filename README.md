# Cardano Node Setup

This repository contains the necessary Docker Compose configurations to set up a Cardano node along with Ogmios and Kupo, which are required for the Charli3 setup.

## Components

- `cardano-node`: Runs the Cardano node with the official inputoutput/cardano-node image.
- `ogmios`: A WebSocket server for Cardano, based on the cardanosolutions/ogmios image.
- `kupo`: A webhook-based service for Cardano node events, using the cardanosolutions/kupo image.

## Quickstart

To launch the Cardano node, Ogmios, and Kupo for the mainnet, ensure Docker is installed on your system and run the following command:

```sh
NETWORK=mainnet docker compose up -d
```

This will start the services defined in the `docker-compose.yml` file.

## Prerequisites

- Docker
- Docker Compose

## Installation

1. Clone this repository.
2. Navigate to the repository directory.
3. Use the provided Docker Compose command to start the services.
