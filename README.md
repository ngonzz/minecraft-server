# Miko

Docker based Minecraft server hosted within Github Codespaces

## Prerequisites

You'll need a free [Ngrok](https://ngrok.com/) account to access the server after creation.  
To configure Ngrok place your [Auth token](https://dashboard.ngrok.com/get-started/your-authtoken) in the `xxxx of --authtoken=xxxx` within the PARAMS environment variable.  
Then find the server's public URL in the [tunnels dashboard](https://dashboard.ngrok.com/tunnels/agents).

## Usage

### Video Guide

[! To be filled](https://user-images.githubusercontent.com/53623449/172069962-cbcf9438-57cf-4f5b-b8a2-f60d87d7aa66.mp4)

### Server Repo

The Docker container is configured to use [itgz's docker-minecraft-server](https://github.com/itzg/docker-minecraft-server) as the Minecraft server, more info on how the server can be configured can be found [here](https://github.com/itzg/docker-minecraft-server/blob/master/README.md).

### Start the server

```bash
docker-compose up -d --force-recreate --remove-orphans
```

### Saving the server data

By default the container's data is stored in the `./server-data` folder (which is created on the first launch of the container). I recommend that you zip and keep the folder stored off codespace after you've finished using the server it's unlikely but possible that the folder or codespace may get deleted along with your save.

- To save the server data to a zip:

```bash
docker-compose down
zip -r server-data.zip server-data
```

- To reload the server data from a zip:

```bash
unzip server-data.zip
docker-compose up -d --force-recreate --remove-orphans
```
