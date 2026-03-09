# Getting Started

This guide covers installing and running BACnet Lab on your machine.

## Prerequisites

- **Python 3.11+** (for local development)
- **Docker** and **Docker Compose** (for containerized deployment)

## Local Development

### Install

```bash
git clone https://github.com/YOUR_USERNAME/bacnet-lab.git
cd bacnet-lab
pip install -e ".[dev]"
```

### Run

```bash
python -m bacnet_lab
```

The application starts on http://localhost:8080. Open http://localhost:8080/ui for the web dashboard.

BACnet devices start listening on UDP ports starting at 47808 (one port per device). They are discoverable by any BACnet client on the same network.

### Run Tests

```bash
pytest
```

Tests use a `FakeNetwork` adapter — no BAC0 or BACnet network required.

## Docker (Linux)

Linux is recommended for production because `network_mode: host` is required for BACnet UDP broadcast to work across the network.

```bash
# Clone the repository
git clone https://github.com/YOUR_USERNAME/bacnet-lab.git
cd bacnet-lab

# Configure authentication (optional)
cp .env.example .env
# Edit .env to set BACNET_LAB_AUTH_USERNAME and BACNET_LAB_AUTH_PASSWORD

# Start
docker compose up -d --build
```

BACnet devices are fully discoverable from any machine on the same subnet.

### Stopping

```bash
docker compose down
```

### Viewing Logs

```bash
docker compose logs -f
```

## Docker (macOS/Windows)

`network_mode: host` only works on Linux. For macOS and Windows, use the development override file which switches to bridge mode with port mapping:

```bash
docker compose -f docker-compose.yml -f docker-compose.dev.yml up --build
```

**Limitations in bridge mode:**
- BACnet devices are **not discoverable** from the host network (UDP broadcast doesn't cross Docker's virtual network)
- The REST API and web dashboard work normally on http://localhost:8080
- You can read/write BACnet points through the REST API

This is suitable for developing against the API and UI. For full BACnet network testing, use a Linux machine or VM.

## First Steps

### 1. Open the Dashboard

Navigate to http://localhost:8080/ui. You'll see an overview of all 7 simulated devices and their current status.

### 2. Start a Scenario

Go to the Scenarios tab and start the **HVAC Day/Night Cycle**. This runs a compressed 24-hour HVAC simulation — you'll see temperatures, valve positions, and fan speeds changing in real time.

### 3. Explore the API

List all devices:

```bash
curl http://localhost:8080/api/devices
```

Get details for a specific device:

```bash
curl http://localhost:8080/api/devices/1001
```

Write a point value:

```bash
curl -X PUT http://localhost:8080/api/devices/1001/points \
  -H "Content-Type: application/json" \
  -d '{"point_name": "AHU-01/CoolingValve", "value": 80.0}'
```

### 4. Set Up a Webhook

Register an endpoint to receive real-time events:

```bash
curl -X POST http://localhost:8080/api/endpoints \
  -H "Content-Type: application/json" \
  -d '{"url": "https://your-server.com/webhook"}'
```

Save the returned `secret` — you'll need it to verify webhook signatures. See [Webhooks documentation](webhooks.md).

## What's Next

- [Devices](devices.md) — learn about the simulated devices and how to create custom ones
- [Scenarios](scenarios.md) — understand the simulation scenarios and their parameters
- [API Reference](api.md) — full REST API documentation
- [Configuration](configuration.md) — environment variables and settings
