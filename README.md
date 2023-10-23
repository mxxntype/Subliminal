![Static Badge](https://img.shields.io/badge/Minecraft_version-1.19.2-a6e3a1?logo=minecraft&logoColor=a6e3a1&labelColor=313244)
![Static Badge](https://img.shields.io/badge/Mod_loader-Forge-fab387?logoColor=fab387&labelColor=313244)
![Static Badge](https://img.shields.io/badge/Docker_image-itzg%2Fminecraft--server-89b4fa?logo=docker&logoColor=89b4fa&labelColor=313244)

## Subliminal 🌱 | Forge `1.19.2` modpack

### Client setup
Use [packwiz](https://packwiz.infra.link/) to export the modpack in `.mrpack` or `.zip` format.
```bash
packwiz modrinth export   # .mrpack
packwiz curseforge export # .zip
```

### Server setup
Use `docker-compose` to spin up a docker container with the server.
```bash
docker compose up -d    # Start the server
docker compose ps       # List active containers
docker compose logs -f  # Show the logs
docker compose down     # Shutdown the server
```

### `docker-compose.yml` example

```yaml
version: '3'
services:
  subliminal-server:
    image: itzg/minecraft-server
    ports:
      - "25565:25565"
    volumes:
      - /opt/subliminal-server:/data
    environment:
      EULA: "TRUE"
      TYPE: "FORGE"
      VERSION: "1.19.2"
      PACKWIZ_URL: "https://raw.githubusercontent.com/mxxntype/Subliminal/main/pack.toml"
      MEMORY: "4G"
      USE_AIKAR_FLAGS: "true"
      MODE: "survival"
      DIFFICULTY: "normal"
      MAX_PLAYERS: "8"
      MOTD: "Packwiz + Docker | Forge 1.19.2"
```

[Docker image documentation](https://docker-minecraft-server.readthedocs.io/en/latest/)
