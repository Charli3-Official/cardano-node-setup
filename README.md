# Cardano Node Setup

This repository contains configurations for setting up a mainnet Cardano node along with Ogmios and Kupo, integral parts of the Charli3 infrastructure.

## Components

- `cardano-node`: Official inputoutput/cardano-node image for running the Cardano node.
- `ogmios`: WebSocket server based on cardanosolutions/ogmios, for interacting with the Cardano node.
- `kupo`: Webhook service from cardanosolutions/kupo, to handle Cardano node events.

## Prerequisites

- Git
- Docker
- Docker Compose

## Installation & Setup

1. Clone this repository with the submodule:
    ```sh
    git clone --recurse-submodules https://github.com/Charli3-Official/cardano-node-setup.git
    ```
   
   If you've already cloned the repository, initialize and update the submodule with:
    ```sh
    git submodule update --init
    ```

2. Navigate to the repository directory:
    ```sh
    cd cardano-node-setup
    ```

3. Start the Cardano node and services with Docker:
    ```sh
    NETWORK=mainnet docker compose up -d
    ```

This will deploy the Cardano node, Ogmios, and Kupo services as defined in the `docker-compose.yml` file.
