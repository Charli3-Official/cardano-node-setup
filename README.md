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

## Updating Configurations and Restarting Nodes

To switch to updated submodule configurations and restart the nodes:

1. Stop services: `NETWORK=mainnet docker compose down`
2. Pull updates: `git pull origin main`
3. Update submodule: `git submodule sync && git submodule update --init --recursive`
4. Restart services: `NETWORK=mainnet docker compose up -d`

Note: As of November 21, 2025, this setup uses Cardano Node 10.1.4, which is below the versions affected by the recent Mainnet issue (10.3.1+), so no upgrade is required.

## Checking Node Status and Sync

To verify the node is running and synced:

1. Check if the node socket exists: `docker exec cardano-wallet-cardano-node-1 ls -la /ipc/`
2. Check Cardano CLI version: `docker exec cardano-wallet-cardano-node-1 cardano-cli --version`
3. Query the blockchain tip for sync status: `docker exec cardano-wallet-cardano-node-1 cardano-cli query tip --mainnet --socket-path /ipc/node.socket`
