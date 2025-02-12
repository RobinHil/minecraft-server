# 🎮 Minecraft Server Docker Setup

Run your own Minecraft server easily with Docker! This repository contains everything you need to get started with a containerized Minecraft server.

## ✨ Features

- 🐳 Easy deployment with Docker Compose
- 🔧 Fully configurable through environment variables
- 📦 Persistent data storage
- 🔒 Whitelist support for private servers
- 🌐 Network configuration with dedicated bridge network
- 🔄 Automatic restart on failure

## 🚀 Quick Start

1. **Clone this repository**
```bash
git clone https://github.com/RobinHil/minecraft-server.git
cd minecraft-server
```

2. **Set up environment variables**
```bash
cp .env.example .env
```

3. **Configure your server**
Edit the `.env` file with your desired settings:
```env
EULA=TRUE                  # Accept Minecraft EULA
TYPE=VANILLA               # Server type
VERSION=1.21.3             # Minecraft version
DIFFICULTY=normal          # Game difficulty
ICON=/icon.png             # Server icon path
SNOOPER_ENABLED=false      # Disable snooper
SPAWN_PROTECTION=10        # Spawn protection radius
PORT=25565                 # Server port
MAX_MEMORY=4G              # Maximum memory allocation
ENABLE_WHITELIST=true      # Enable whitelist
WHITELIST=Player1,Player2  # Whitelisted players
OVERRIDE_WHITELIST=true    # Override existing whitelist
```

4. **Add your server icon (optional)**
- Place your server icon as `icon.png` in the root directory
- Image must be 64x64 pixels

5. **Start the server**
```bash
docker compose up -d
```

## 📝 Configuration

### Environment Variables

| Variable | Description | Default |
|----------|-------------|---------|
| `EULA` | Accept Minecraft EULA | `TRUE` |
| `TYPE` | Server type (VANILLA, FORGE, etc.) | `VANILLA` |
| `VERSION` | Minecraft version | `1.21.3` |
| `DIFFICULTY` | Game difficulty | `normal` |
| `PORT` | Server port | `25565` |
| `MAX_MEMORY` | Maximum memory allocation | `4G` |
| `ENABLE_WHITELIST` | Enable player whitelist | `true` |
| `WHITELIST` | Comma-separated list of players | empty |

### 🗄️ Data Persistence
All server data is stored in a Docker volume named `minecraft_data`

### 🔒 Security
- Whitelist is enabled by default
- Spawn protection is set to 10 blocks
- Snooper is disabled by default

## 🔧 Advanced Configuration

The server uses the [itzg/minecraft-server](https://hub.docker.com/r/itzg/minecraft-server) Docker image which offers many additional configuration options. Check the official documentation for more details.

## 🛠️ Maintenance

### View logs
```bash
docker compose logs -f minecraft
```

### Stop server
```bash
docker compose down
```

## 📜 License
- This project uses the official Minecraft server which is subject to the [Minecraft EULA](https://www.minecraft.net/en-us/eula).
- Thanks to itzg for his [itzg/minecraft-server](https://hub.docker.com/r/itzg/minecraft-server) Docker image which is this project base

## ⚠️ Note
Make sure to always backup your world data before making any major changes!
