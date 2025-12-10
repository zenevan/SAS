# TorilLib

> A comprehensive Mudlet package for TorilMUD, providing advanced GUI, combat assistance, character management, and world navigation tools.

[![Version](https://img.shields.io/badge/version-0.1.0--dev-blue)]()
[![License](https://img.shields.io/badge/license-MIT-green)]()
[![Mudlet](https://img.shields.io/badge/mudlet-4.0%2B-orange)]()

---

## 🎮 Overview

TorilLib is a feature-rich Mudlet package designed specifically for TorilMUD (torilmud.org:9999). It provides an extensive set of tools to enhance your gaming experience, from visual interfaces to combat automation and world exploration.

### Key Features

✨ **Comprehensive GUI System**
- Multiple information containers (Map, Combat, Powers, Equipment, etc.)
- Customizable layouts and themes
- Real-time updates

🗺️ **Advanced Map Integration**
- Interactive map visualization
- Pathfinding and auto-navigation
- Area database with points of interest

⚔️ **Combat Assistance**
- Target tracking and damage meters
- Cooldown management
- Combat rotations and queues

👤 **Character Management**
- Complete class and race database
- Equipment and stat tracking
- Skill and spell progression

🎯 **Quality of Life**
- Quest tracking
- Inventory management
- Automation tools

---

## 📦 Installation

### Requirements
- **Mudlet**: Version 4.0 or higher
- **TorilMUD Account**: Active account on torilmud.org
- **Lua**: 5.1+ (included with Mudlet)

### Quick Install

1. Download the latest release from [Releases](#)
2. Open Mudlet
3. Go to Package Manager
4. Click "Install"
5. Select the downloaded TorilLib package
6. Connect to TorilMUD
7. Enjoy!

### Manual Install

```bash
# Clone repository
git clone https://github.com/your-org/TorilLib.git

# Copy to Mudlet profiles directory
# Windows: %APPDATA%/Mudlet/profiles/[profile]/
# Mac: ~/Library/Application Support/Mudlet/profiles/[profile]/
# Linux: ~/.config/mudlet/profiles/[profile]/
```

---

## 🚀 Quick Start

### First Time Setup

1. **Connect to TorilMUD**
   ```
   Connect to torilmud.org:9999
   ```

2. **Initialize TorilLib**
   ```lua
   TorilLib:init()
   ```

3. **Configure Settings**
   ```lua
   TorilLib:showSettings()
   ```

4. **Enable Desired Features**
   ```lua
   TorilLib.GUI:enable()
   TorilLib.Combat:enable()
   TorilLib.Map:enable()
   ```

### Basic Commands

```lua
-- GUI Controls
/tl gui show        -- Show all GUI containers
/tl gui hide        -- Hide all GUI containers
/tl gui reset       -- Reset to default layout

-- Map Commands
/map_export         -- Export current map
/map_open           -- Open map in browser
/map_link           -- Get current area link

-- Combat Commands
/tl combat start    -- Start combat tracking
/tl combat stop     -- Stop combat tracking
/tl combat reset    -- Reset combat stats

-- Character Commands
/tl char show       -- Show character sheet
/tl char stats      -- Display statistics
/tl char equipment  -- Show equipment
```

---

## 📖 Documentation

### User Documentation
- **[Installation Guide](./docs/installation.md)** - Detailed setup instructions
- **[User Guide](./docs/user-guide.md)** - Feature walkthroughs
- **[Configuration](./docs/configuration.md)** - Settings and customization
- **[Troubleshooting](./docs/troubleshooting.md)** - Common issues and solutions
- **[FAQ](./docs/faq.md)** - Frequently asked questions

### Developer Documentation
- **[Architecture](./docs/architecture.md)** - System design overview
- **[API Reference](./docs/api.md)** - Function documentation
- **[Database Schema](./docs/database.md)** - Data structures
- **[Contributing](./CONTRIBUTING.md)** - How to contribute
- **[Development Setup](./docs/development.md)** - Dev environment

### Project Management
- **[Roadmap](./ROADMAP.md)** - Development roadmap
- **[Changelog](./CHANGELOG.md)** - Version history
- **[Feature Backlog](./roadmap/feature-backlog.md)** - Planned features

---

## 🗺️ Roadmap

TorilLib development is organized into 7 phases:

| Phase | Focus | Status | Timeline |
|-------|-------|--------|----------|
| [Phase 1](./roadmap/phase-1-foundation.md) | Foundation | 80% | Q1 |
| [Phase 2](./roadmap/phase-2-gui.md) | GUI & Visualization | 30% | Q2 |
| [Phase 3](./roadmap/phase-3-character.md) | Character Management | 20% | Q2-Q3 |
| [Phase 4](./roadmap/phase-4-combat.md) | Combat System | 10% | Q3 |
| [Phase 5](./roadmap/phase-5-map.md) | Map & Navigation | 40% | Q3-Q4 |
| [Phase 6](./roadmap/phase-6-advanced.md) | Advanced Features | 0% | Q4 |
| [Phase 7](./roadmap/phase-7-polish.md) | Polish & Optimization | 0% | Q4-Q1 |

See the [complete roadmap](./ROADMAP.md) for detailed information.

---

## 🎯 Features

### Current Features

#### GUI System ✅
- Map container with visualization
- Room information display
- Atlas for area navigation
- Group member tracking
- Equipment display
- Combat information
- Powers and abilities

#### Database ✅
- 15+ classes with full ability lists
- 15 races (good and evil)
- Complete skills database
- Comprehensive spells database
- Combat powers by class
- Server configuration

#### Map Integration ✅
- Map export/import
- HTML visualization
- Room coordinates
- Exit tracking
- Custom lines support

### Coming Soon

#### Character Management ⏳
- Auto-detected character profiles
- Real-time stat tracking
- Equipment manager
- Progression tracker
- Buff/debuff monitoring

#### Combat System ⏳
- Target tracking
- Cooldown management
- Damage meters
- Combat rotations
- Healing assistance

#### Navigation ⏳
- Pathfinding
- Auto-walk
- Area database
- Points of interest
- Travel automation

---

## 🤝 Contributing

We welcome contributions! Here's how you can help:

### For Users
- Report bugs via [GitHub Issues](#)
- Request features in [Feature Backlog](./roadmap/feature-backlog.md)
- Share your TorilLib setups
- Help other users in Discord

### For Developers
- Check [Contributing Guide](./CONTRIBUTING.md)
- Look for `good first issue` labels
- Join development discussions
- Submit pull requests

### Ways to Contribute
- 🐛 Bug fixes
- ✨ New features
- 📝 Documentation
- 🎨 UI/UX improvements
- 🧪 Testing
- 🌍 Translations

---

## 📊 Project Structure

```
TorilLib/
├── init.lua              # Main initialization
├── config.lua            # Configuration
├── ROADMAP.md            # Development roadmap
├── CHANGELOG.md          # Version history
├── CONTRIBUTING.md       # Contribution guidelines
├── README.md             # This file
│
├── roadmap/              # Detailed phase documents
│   ├── phase-1-foundation.md
│   ├── phase-2-gui.md
│   ├── phase-3-character.md
│   ├── phase-4-combat.md
│   ├── phase-5-map.md
│   ├── phase-6-advanced.md
│   ├── phase-7-polish.md
│   └── feature-backlog.md
│
├── data/                 # Game data files
│   ├── Classes.sql       # Class definitions
│   ├── Skills.sql        # Skills database
│   ├── Spells.sql        # Spells database
│   ├── Powers.sql        # Powers database
│   ├── Races.txt         # Race definitions
│   └── Server.sql        # Server config
│
├── src/                  # Source code (TBD)
│   ├── core/            # Core systems
│   ├── gui/             # GUI components
│   ├── combat/          # Combat system
│   ├── character/       # Character management
│   ├── map/             # Map integration
│   └── utils/           # Utilities
│
├── docs/                 # Documentation
└── tests/                # Test suite
```

---

## 🛠️ Technology Stack

- **Language**: Lua 5.1+
- **Client**: Mudlet 4.0+
- **MUD**: TorilMUD (DikuMUD derivative)
- **UI**: HTML/CSS/JavaScript (for map viewer)
- **Version Control**: Git
- **Testing**: Busted (planned)

---

## 🔧 Configuration

### Basic Configuration

```lua
-- TorilLib Configuration
TorilLib.Config = {
    -- GUI Settings
    gui = {
        enabled = true,
        theme = "dark",
        containers = {
            map = true,
            combat = true,
            equipment = true
        }
    },
    
    -- Combat Settings
    combat = {
        tracking = true,
        damage_meter = true,
        cooldowns = true
    },
    
    -- Map Settings
    map = {
        auto_update = true,
        pathfinding = true
    }
}
```

See [Configuration Guide](./docs/configuration.md) for all options.

---

## 📸 Screenshots

*(Coming soon - Add screenshots of GUI, map, combat tracking, etc.)*

---

## 🆘 Support

### Getting Help
- **Discord**: [Join our server](#)
- **Forums**: [Visit forums](#)
- **GitHub Issues**: [Report bugs](#)
- **Wiki**: [Browse wiki](#)

### Common Issues
- See [Troubleshooting Guide](./docs/troubleshooting.md)
- Check [FAQ](./docs/faq.md)
- Search existing issues

---

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details.

---

## 🙏 Acknowledgments

### Contributors
- [List of contributors]

### Special Thanks
- TorilMUD staff and community
- Mudlet development team
- All beta testers
- Feature requesters

### Built With
- [Mudlet](https://www.mudlet.org/) - The MUD client
- [TorilMUD](https://www.torilmud.com/) - The game
- Many community contributions

---

## 📞 Contact

- **Project Lead**: [Your Name]
- **Email**: contact@torillib.com
- **Discord**: [Server Invite](#)
- **GitHub**: [Repository](#)

---

## 🔗 Links

- [TorilMUD Website](https://www.torilmud.com/)
- [TorilMUD News](http://news.torilmud.com/)
- [TorilMUD Discord](https://discord.gg/t7edjzM)
- [Mudlet Website](https://www.mudlet.org/)
- [Mudlet Manual](https://wiki.mudlet.org/)

---

## 📈 Status

**Current Version**: 0.1.0-dev  
**Status**: Early Development  
**Last Updated**: 2024-12-10

**Build Status**: ![Development](https://img.shields.io/badge/build-development-yellow)  
**Test Coverage**: ![Not Available](https://img.shields.io/badge/coverage-n%2Fa-lightgrey)

---

## ⭐ Star History

If you find TorilLib useful, please consider starring the repository!

---

Made with ❤️ for the TorilMUD community

**Happy MUDding!** 🎮
