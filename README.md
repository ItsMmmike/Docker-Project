# Docker-Project: Minecraft Server
Docker Minecraft Server and Server Monitor Build for SYS-265

## Overview
Purpose: The goal of this project is to learn how to use docker to configure and build a Minecraft server as well as a monitoring stack to keep track of the server status.

### Elements of Build

**Minecraft Server**
* Minecraft Server - Service hosting a multiplayer Minecraft Java Edition server

**Monitoring Stack**
* Grafana - Open Source Dashboard Service used to monitor graphs and alerts from its configured data sources (Will be used as a dashboard to monitor our Minecraft server)
* Prometheus - Open Source systems monitoring and alerting toolkit used to collect and store metric information from client devices (Provides the database and metric information for Grafana dashboard)
* Cadvisor - (Container Advisor) Open Source utility used to monitor the status of containers (Provides container resource information on our Minecraft server)
* mc-monitor - Agent used to monitor the status of Docker Minecraft Servers

### Initial Setup
> Pre-Req: Make sure have docker setup on your system before configuring the Minecraft server (Ex. docker01 - Ubuntu Server 22.04 LTS)
* Install git using `sudo apt install git`
* Navigate to the desired location to install the Docker-Project config files
* Then use the following git command to pull the docker config files from this repository `sudo git clone https://github.com/ItsMmmike/Docker-Project`

### How to use with Docker Compose
* After downloading the following config files from this repository, move to the directory `Docker-Project`
* Run `docker-compose up -d` (this should now start the Minecraft server and monitoring services)
* Use the `docker ps` command to verify that all containers are up running.
* To stop the Minecraft server, run `docker-compose down` or `docker stop <list-all-docker-conatiners-here>`

### Accessing the Grafana Server Monitoring Dashboard
* On local desktop (either Mgmt01 or Wks01) browse to the follwoing URL at `http:<IP/Hostname-of-docker_server>:3000` to access the Grafana Dashboard.
* Log in using the default credentials (U:"admin", P:"admin"), you should be promted to change the password after completing this step.
* Once you reach the home screen, we can view the status of our Minecraft server by selecting `Dashboard` > `Browse` > `MC Monitor`

![image](https://github.com/ItsMmmike/Docker-Project/assets/113321364/fe5e35a5-020f-40d7-a541-049bd36a14a2)

> Figure 1: Screenshot of me viewing the status of the docker minecraft server via Grafana MC Monitor Dashboard

### Accessing the Server as a Client
* Before joining the Minecraft Server, make sure that you have an up-to-date version of the game. [Minecraft Download Link Here](https://www.minecraft.net/en-us/download)
* After openening the game, you can navigate to `Multiplayer` and then to `Add Server`. From here we can enter a Server Name and enter the IP/Hostname of our docker system running the Minecraft Server Container (ex. Docker01).
* After clicking `Done` you should now be able to join the Minecraft server

![image](https://github.com/ItsMmmike/Docker-Project/assets/113321364/617f2015-f06d-4151-b438-5dcd4382354e)

> Figure 2: Screenshot of the Docker Minecraft server successfully configured on the Minecraft client.

## Credit
* This project was modified using an example from [itzg's mc-monitor](https://github.com/itzg/mc-monitor)

