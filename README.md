# ConnectHub - Advanced Minecraft Lobby Plugin

## Overview
ConnectHub is a feature-rich Minecraft lobby plugin designed to create an engaging and interactive hub experience for your server network. It includes various features such as minigames, cosmetics, player statistics, and server management tools.

## Features

### 🎮 Core Features
- **Server Navigation System**
  - Interactive GUI-based server selector
  - Real-time server status and player count
  - Custom teleportation points

- **Player Management**
  - Player visibility toggles
  - Advanced permission system
  - Player statistics tracking

### 🎨 Cosmetic System
- **Outfit System**
  - Multiple armor sets
  - Custom textures support
  - Animated cosmetics

- **Particle Effects**
  - Various particle trails
  - Custom particle combinations
  - Toggle options

### 🎯 Minigames
- **Parkour System**
  - Checkpoint system
  - Time tracking
  - Leaderboards

- **Spleef Arena**
  - Automated game management
  - Score tracking
  - Multiple arena support

### 💎 Progression System
- **Player Levels**
  - Experience system
  - Level-based rewards
  - Custom level paths

- **Daily Rewards**
  - Streak bonuses
  - Custom reward configuration
  - GUI-based claim system

### 👥 Social Features
- **Friend System**
  - Friend list management
  - Online status tracking
  - Quick join functionality

- **Statistics**
  - Playtime tracking
  - Achievement system
  - Detailed player stats

## Installation

1. Download the latest release from the releases page
2. Place the JAR file in your server's `plugins` folder
3. Restart your server
4. Configure the plugin in the generated `config.yml`

## Configuration

### Basic Configuration

# config.yml example
settings:
  prefix: "&8[&bConnectHub&8]"
  database:
    type: "MySQL"  # or "SQLite"
    host: "localhost"
    port: 3306
    database: "connecthub"
    username: "user"
    password: "pass"

features:
  particles:
    enabled: true
    default-effect: "FLAME"
  
  minigames:
    enabled: true
    parkour:
      enabled: true
      checkpoint-interval: 30

### Permissions

permissions:
  connecthub.admin:
    description: Gives access to all ConnectHub admin commands
    default: op
  
  connecthub.vip:
    description: Gives access to VIP features
    default: false

  connecthub.particles:
    description: Allows usage of particle effects
    default: true

## Commands

### Admin Commands
- `/ch reload` - Reload the plugin configuration
- `/ch setspawn` - Set the lobby spawn point
- `/ch addserver <name>` - Add a server to the network

### Player Commands
- `/lobby` - Teleport to the lobby
- `/particles` - Open particle effect menu
- `/stats` - View your statistics
- `/friend <add|remove|list> [player]` - Friend system commands

## API

### Maven

<repository>
    <id>connecthub-repo</id>
    <url>https://repo.example.com/maven</url>
</repository>

<dependency>
    <groupId>org.example</groupId>
    <artifactId>connecthub</artifactId>
    <version>1.0-SNAPSHOT</version>
    <scope>provided</scope>
</dependency>

### Example Usage

public class ExamplePlugin extends JavaPlugin {
    @Override
    public void onEnable() {
        ConnectHub api = ConnectHub.getAPI();
        api.getPlayerManager().getPlayerStats(player);
    }
}

## Development

### Building from Source
1. Clone the repository

git clone https://github.com/yourusername/connecthub.git

2. Build using Maven

cd connecthub
mvn clean package

### Contributing
1. Fork the repository
2. Create a new branch for your feature
3. Submit a pull request

## Support

- Discord: [Join our Discord](https://discord.gg/example)
- Issues: [GitHub Issues](https://github.com/yourusername/connecthub/issues)
- Wiki: [Documentation](https://github.com/yourusername/connecthub/wiki)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Credits

- Lead Developer: [Your Name]
- Contributors: [List of Contributors]
- Special thanks to the Spigot community

## Changelog

### Version 1.0.0
- Initial release
- Basic lobby functionality
- Particle system implementation
- Minigames system

### Version 1.1.0
- Added friend system
- Improved particle effects
- Bug fixes and performance improvements