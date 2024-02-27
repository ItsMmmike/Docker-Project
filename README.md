# Docker-Project: Minecraft Server
Docker Minecraft Server and Server Monitor Build for SYS-265

## Overview
Purpose: The goal of this project is to learn how to use docker to configure and build a minecraft server as well as a monitoring stack to keep track of the server status.

### Elements of Build

**Minecraft Server**
* Minecraft Server - Service hosting a multiplayer minecraft server

**Monitoring Stack**
* Grafana - Open Source Dashboard Service used to monitor graphs and alerts from its configured data sources (Will be used as a dashboard to monitor our minecraft server)
* Prometheus - Open Source systems monitoring and alerting toolkit used to collect and store metric information from client devices (Provides the database and metric information for Grafana dashboard)
* Cadvisor - (Container Advisor) Open Source utility used to monitor the status of containers (Provides container resrouce information on our minecraft server)
* mc-monitor - Agent used to monitor the status of Docker Minecraft Servers

### Setup
> Pre-Req: Make sure have docker setup on your system before configuring the minecraft server (Ex. docker01 - Ubuntu Server 22.04 LTS)
* Install git using `sudo apt install git`
* Navigate to the desired location to install the minecraft-servermon config files
* Then use the following git command to pull the docker config files from this repository `sudo git clone https://github.com/ItsMmmike/Docker-Project`

### How to use
* After downloading the following config files from this repository, move to the directory `Minecraft-Servermon`
* Run `docker-compose up -d` (this should now start the minecraft server and monitoring services)
* Use the `docker ps` command to verify that all containers are up running.
* To stop the minecraft server, run `docker stop <list-all-docker-conatiners-here>`

## Credit
* This project was modified using an example from [itzg's mc-monitor](https://github.com/itzg/mc-monitor)

