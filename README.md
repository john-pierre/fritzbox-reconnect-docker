# FritzBox Reconnect Docker

![Docker Image](https://img.shields.io/badge/docker-ready-blue)
![License: GPL v3](https://img.shields.io/badge/license-GPL%20v3-blue)
![Build Status](https://img.shields.io/github/actions/workflow/status/your-repo/fritzbox-reconnect-docker/build.yml)

## Table of Contents
1. [Overview](#overview)
2. [Prerequisites](#prerequisites)
3. [Installation](#installation)
4. [Usage](#usage)
5. [Environment Variables](#environment-variables)
6. [Logging](#logging)
7. [License](#license)

## Overview
This Docker container automatically reconnects a FritzBox router every night at 3:00 AM using the TR-064 interface.

## Prerequisites
- Docker installed on your system
- A FritzBox router with TR-064 enabled

## Installation
1. Clone this repository:
   ```sh
   git clone <repository-url>
   cd fritzbox-reconnect-docker
   ```
2. Build the Docker image:
   ```sh
   docker build -t fritzbox-reconnect .
   ```

## Usage
Run the container with the required environment variables:
```sh
docker run -d --name fritzbox-reconnect \
  -e FRITZBOX_IP="192.168.178.1" \
  -e FRITZBOX_USER="your_username" \
  -e FRITZBOX_PASSWORD="your_password" \
  fritzbox-reconnect
```

## Environment Variables
- `FRITZBOX_IP` (default: `192.168.178.1`): The IP address of your FritzBox router.
- `FRITZBOX_USER`: Your FritzBox username.
- `FRITZBOX_PASSWORD`: Your FritzBox password.

## Logging
The container logs directly to `stdout`, so you can check the logs using:
```sh
docker logs -f fritzbox-reconnect
```

## License
This project is licensed under the **GNU General Public License v3.0**. See the [LICENSE](LICENSE) file for details.

---

*This project is not affiliated with AVM or the FritzBox brand.*

