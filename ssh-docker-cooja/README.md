# Cooja Simulation Environment

This directory provides a Docker-based setup for running **Cooja simulations** with a multi-container architecture.

## Features

- **Cooja Simulator**: Contiki-NG's Cooja simulator with support for MSP430.

## Prerequisites

Before using this setup, ensure you have the following installed:

- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)

## Directory Structure

```
project-root/
├── cooja/
│   ├── Dockerfile                # Cooja Dockerfile
│   ├── simulation/
│   │   ├── simulation_config.xml # Simulation configuration
├── logs/                         # Shared directory for logs
├── docker-compose.yml            # Multi-container configuration
```

## How to Use

### Step 1: Build and Start Containers
Run the following commands to build and start the Docker containers:

```bash
docker compose build
docker compose up -d
```

### Step 2: Connect to the Cooja Simulator
After the containers are running, connect to the Cooja simulator using SSH:

```bash
ssh root@localhost -p 2223
```

The root password is set to `root`.

### Step 3: Run a Simulation
Run the following command inside the Cooja container to start a simulation:

```bash
cd /opt/contiki-ng/tools/cooja
```

```bash
java -Xms4g -Xmx4g -jar build/libs/cooja.jar --no-gui sim-config.csc
```

## Customizing Configurations

- **Simulation Configuration**: Edit `cooja/simulation/simulation_config.xml` to modify the simulation parameters.

## Stopping and Cleaning Up

To stop the containers:

```bash
docker compose down
```

To remove all containers, volumes, and images:

```bash
docker compose down --rmi all --volumes
```

---

## Troubleshooting

- **Java Not Found in SSH Session**: Ensure the `PATH` variable includes the Java binary path. This is set automatically in the provided Dockerfile.
- **Simulation Errors**: Verify the simulation configuration file `sim-config.csc` and ensure the necessary plugins are correctly defined.

Feel free to customize this setup as per your requirements!