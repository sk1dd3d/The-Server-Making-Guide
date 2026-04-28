# 🎮 The Minecraft Server Making Guide

> A comprehensive guide for setting up, configuring, and managing your own Minecraft server — from choosing a host to advanced optimization.

---

## Table of Contents

1. [Choosing a Host](#1-choosing-a-host)
2. [Choosing a Version](#2-choosing-a-version)
3. [Choosing Your Server Software](#3-choosing-your-server-software)
4. [Essential Plugins](#4-essential-plugins)
5. [Recommended Plugins by Category](#5-recommended-plugins-by-category)
6. [Server Configuration](#6-server-configuration)
7. [World & Map Setup](#7-world--map-setup)
8. [Permission Management with LuckPerms](#8-permission-management-with-luckperms)
9. [Setting Up Ranks & Groups](#9-setting-up-ranks--groups)
10. [Economy Setup](#10-economy-setup)
11. [Anti-Cheat & Security](#11-anti-cheat--security)
12. [Performance Optimization](#12-performance-optimization)
13. [Backups](#13-backups)
14. [Connecting Players & Networking](#14-connecting-players--networking)
15. [Moderation Tools](#15-moderation-tools)
16. [Common Issues & Troubleshooting](#16-common-issues--troubleshooting)
17. [Tips & Best Practices](#17-tips--best-practices)

---

## 1. Choosing a Host

Where your server runs matters a lot for performance and uptime.

### Option A — Host on Your Own PC
Running a server on your own machine is possible but **not recommended** for public servers due to:
- Inconsistent uptime (server goes offline when you close your PC)
- Your internet upload speed limits how many players can connect
- Security risks (your IP is exposed)

If you still want to run locally, use a tool like **ngrok** or **playit.gg** to expose the server without revealing your home IP.

### Option B — Dedicated Hosting (Recommended)

| Host | Price | Notes |
|------|-------|-------|
| [Aternos](https://aternos.org) | Free | Limited performance, queued starts, good for testing |
| [Minehut](https://minehut.com) | Free / Paid tiers | Easy setup, limited free tier |
| [ByteHosting](https://bytehosting.cloud) | Paid | Good performance, Brazilian hosting available |
| [Shockbyte](https://shockbyte.com) | Paid | Very popular, reliable, global locations |
| [Apex Hosting](https://apexminecrafthosting.com) | Paid | Easy panel, beginner-friendly |
| [PebbleHost](https://pebblehost.com) | Paid | Budget-friendly, good value |
| [BisectHosting](https://bisecthosting.com) | Paid | Great for modpacks, many locations |

**Tip:** For a serious public server, aim for at least **2–4 GB of RAM** and a host with SSD storage and a good CPU (look for Ryzen or similar modern processors).

---

## 2. Choosing a Version

Not all versions are equal. Here's what to consider:

### Recommended Versions

| Version | Notes |
|---------|-------|
| **1.20.1** | Most plugin-compatible version; huge ecosystem of plugins and mods |
| **1.21.1** | Good stability, solid plugin support |
| **1.21.4** | Latest stable; fewer plugins available but growing fast |

### Version Considerations

- **Older versions (1.8–1.12):** Used mainly for PvP servers (1.8 PvP mechanics). Plugin support is limited to old versions.
- **1.16.5:** Solid Nether update version, still widely supported.
- **1.20.1:** Sweet spot — has the most plugin support across all major platforms.
- **Latest (1.21.x):** Exciting features but fewer plugin updates. Best if you're starting fresh and not relying on many specific plugins.

> **Recommendation:** Start with **1.20.1** for best compatibility. If you don't need legacy plugins, **1.21.1** is also a great choice.

---

## 3. Choosing Your Server Software

Your server software determines performance, plugin support, and extra features.

### Software Overview

| Software | Based On | Plugins | Best For |
|----------|----------|---------|----------|
| **Vanilla** | Official Mojang | None | Pure vanilla experience |
| **CraftBukkit** | Bukkit API | Bukkit/Spigot | Legacy, not recommended |
| **Spigot** | CraftBukkit | Bukkit/Spigot | Stable, widely supported |
| **Paper** | Spigot | Bukkit/Spigot/Paper | Most servers — great performance |
| **Purpur** | Paper | Bukkit/Spigot/Paper/Purpur | Extra config options on top of Paper |
| **Folia** | Paper | Limited (Folia-compatible only) | Large servers with many players |
| **Fabric** | Fabric Loader | Fabric Mods | Modded lightweight servers |
| **Forge** | Forge Loader | Forge Mods | Heavy modpacks |
| **Sponge** | Sponge API | Sponge plugins | Advanced plugin developers |

### Recommendations

- **Paper** — Best default choice. Massive performance improvements over Spigot, compatible with almost all plugins.
- **Purpur** — Use if you want extra mob behavior tweaks, sit-on-stairs feature, and more configuration. Based on Paper so all Paper plugins work.
- **Folia** — Use only if you have a very large player count (50+) and know what you're doing. Many plugins are incompatible.
- **Fabric + Lithium/Featherlight** — Use for a lightweight modded server with performance mods.

> **Download Paper:** [https://papermc.io/downloads](https://papermc.io/downloads)  
> **Download Purpur:** [https://purpurmc.org](https://purpurmc.org)

---

## 4. Essential Plugins

These are the **must-have** plugins for any server. Install these first.

### EssentialsX (Core)
The backbone of almost every server. Provides basic commands and utilities.

- **EssentialsX** — Main plugin: `/home`, `/spawn`, `/tpa`, `/warp`, `/kit`, `/msg`, `/gamemode`, etc.
- **EssentialsX Chat** — Formats chat with prefixes/suffixes from your permission plugin
- **EssentialsX Spawn** — Controls spawn behavior and first-join spawn

> Download: [https://essentialsx.net](https://essentialsx.net)

### LuckPerms (Permissions)
The best and most flexible permissions plugin available.

- Manage ranks, groups, and individual player permissions
- Web editor available at [https://luckperms.net/editor](https://luckperms.net/editor)
- Works seamlessly with EssentialsX

> Download: [https://luckperms.net](https://luckperms.net)

### Vault (Economy Bridge)
Required by most economy and permission plugins as a bridge/API.

- Does not provide features itself — it's a dependency
- Required for EssentialsX economy and shop plugins

> Download: [https://www.spigotmc.org/resources/vault.34315/](https://www.spigotmc.org/resources/vault.34315/)

---

## 5. Recommended Plugins by Category

### 🛡️ Anti-Cheat
| Plugin | Description |
|--------|-------------|
| **Grim Anticheat** | Best free/open-source anticheat for modern versions. Checks movement, combat, and more |
| **NoCheatPlus (NCP)** | Classic anticheat, still usable but less maintained |
| **Spartan** | Paid anticheat, good detection rates |
| **Matrix** | Paid, well-maintained, popular on minigame servers |

> **Recommended:** Grim for free, Matrix or Spartan if you want paid support

### 🌍 World Management
| Plugin | Description |
|--------|-------------|
| **WorldEdit** | In-game map editing with selections, copy/paste, fill, etc. Essential for builders |
| **WorldGuard** | Region protection — protect areas from griefing and control who can build where |
| **Multiverse-Core** | Manage multiple worlds (creative world, survival world, games world, etc.) |
| **Multiverse-Portals** | Create portals between your Multiverse worlds |
| **VoidGen** | Generate empty/void worlds for creative or hub servers |

### 💰 Economy
| Plugin | Description |
|--------|-------------|
| **EssentialsX Economy** | Included with EssentialsX; basic player balance and transactions |
| **CMI** | All-in-one plugin that includes economy (paid, but comprehensive) |
| **ShopGUI+** | Paid but very popular server shop with GUI interface |
| **QuickShop Hikari** | Free player shop plugin — let players create their own chest shops |
| **DeluxeMenus** | Create custom GUI menus for shops, crates, etc. |

### 🏠 Land Protection & Claims
| Plugin | Description |
|--------|-------------|
| **GriefPrevention** | Classic land claiming with a golden shovel. Free and reliable |
| **Lands** | Modern land claiming with town and nation systems. Highly recommended |
| **SuperiorSkyblock2** | If running a Skyblock server — full island management |
| **BentoBox + BSkyBlock** | Modular Skyblock/OneBlock platform |

### 🎮 Minigames & Fun
| Plugin | Description |
|--------|-------------|
| **MiniGamesLib** | Framework for building minigames |
| **BedWars1058** | Full BedWars implementation |
| **SkyWars** | SkyWars minigame |
| **Duels** | Lets players challenge each other to 1v1 duels |
| **MythicMobs** | Create custom mobs with special abilities, drops, and AI |
| **ModelEngine** | Custom 3D mob/NPC models in-game (requires resource pack) |

### 🗣️ Chat & Communication
| Plugin | Description |
|--------|-------------|
| **EssentialsX Chat** | Basic chat formatting with group prefixes |
| **DiscordSRV** | Bridges your Minecraft chat with a Discord server |
| **VentureChat** | Advanced chat channels (local, global, staff, etc.) |
| **ChatControl Red** | Comprehensive chat management with filters and formatting |
| **InteractiveChat** | Allows players to preview items and inventories in chat |

### 📊 Stats & Scoreboards
| Plugin | Description |
|--------|-------------|
| **TAB** | Fully customizable TAB list and scoreboard |
| **AnimatedScoreboard** | Animated sidebar scoreboard |
| **PlaceholderAPI** | Essential — provides placeholders (variables) used by almost all display plugins |
| **FeatherBoard** | Animated scoreboards with conditions |

> **Important:** Install **PlaceholderAPI** — nearly every display plugin depends on it.

### 🔧 Admin & Utility
| Plugin | Description |
|--------|-------------|
| **CoreProtect** | Block logging — see who placed/broke every block. Essential for rollbacks |
| **spark** | Performance profiler — diagnose lag and TPS drops |
| **Chunky** | Pre-generate your world chunks to eliminate lag spikes from new chunk generation |
| **FastChunkPregenerator** | Alternative to Chunky |
| **CommandPanels** | Create custom command menus/GUIs |
| **Citizens** | Create NPCs that players can interact with |
| **Shopkeepers** | Create NPC traders using Citizens |

### 🎨 Cosmetics & QoL
| Plugin | Description |
|--------|-------------|
| **ItemsAdder** | Add custom items, blocks, mobs, and HUD elements (requires resource pack) |
| **Oraxen** | Alternative to ItemsAdder for custom content |
| **AuthMe** | Player authentication system (important for cracked servers) |
| **SkinsRestorer** | Let players change their skins (crucial for offline/cracked servers) |
| **Votifier + SuperbVote** | Reward players for voting for your server on listing sites |

---

## 6. Server Configuration

### server.properties (Key Settings)

Located at `server.properties` in your server root folder.

```properties
# Server name shown in server list
motd=§aWelcome to My Server! §7| §61.20.1

# Max players
max-players=50

# Difficulty: peaceful, easy, normal, hard
difficulty=normal

# Online mode: true = requires valid Minecraft account, false = cracked server
online-mode=true

# View distance (chunks): lower = less lag
view-distance=8

# Simulation distance (entity/mob activity range)
simulation-distance=6

# Spawn protection radius (blocks around spawn no one can break)
spawn-protection=16

# Enable command blocks
enable-command-block=true

# PVP on or off globally
pvp=true

# Allow players to travel to Nether
allow-nether=true

# Allow The End
allow-the-end=true

# Max world size (radius in blocks)
max-world-size=29999984
```

### paper.yml / paper-global.yml Optimizations

Key settings in `config/paper-global.yml` (Paper 1.19+):

```yaml
chunk-loading-advanced:
  auto-config-send-distance: true
  player-max-concurrent-chunk-loads: 4
  player-max-concurrent-chunk-generates: 4

misc:
  lag-compensate-block-breaking: true
  use-alternative-luck-formula: false
```

### spigot.yml Optimizations

```yaml
world-settings:
  default:
    mob-spawn-range: 6        # Default: 8, reduce for performance
    entity-activation-range:
      animals: 16             # Default: 32
      monsters: 24            # Default: 32
      misc: 8                 # Default: 16
    merge-radius:
      item: 2.5               # Merge dropped items nearby
      exp: 3.0
```

---

## 7. World & Map Setup

### Pre-Generating Your World (Highly Recommended)

Before opening your server to players, pre-generate your world to avoid lag from new chunk generation.

Using **Chunky**:
```
/chunky world world
/chunky radius 5000
/chunky start
```
This generates chunks in a 5000 block radius. Adjust based on your expected player count.

### Setting Up a Spawn

1. Build or download a spawn area
2. Stand at the center of your spawn
3. Run `/setspawn` (EssentialsX)
4. To set the spawn for first-time joiners: `/espawn setspawn`

### Multiple Worlds with Multiverse

```
# Create a new world
/mv create creative NORMAL

# Create a void world (for hub/lobby)
/mv create hub NORMAL -g VoidGen

# Teleport between worlds
/mv tp <world>

# List all worlds
/mv list
```

### World Borders

Set a border to prevent the world from growing infinitely (saves disk space and improves performance):

```
/worldborder set 10000
/worldborder center 0 0
```

---

## 8. Permission Management with LuckPerms

### Basic Concepts

- **Permissions** — Individual access keys (e.g., `essentials.fly`, `essentials.gamemode`)
- **Groups** — Collections of permissions (e.g., `default`, `vip`, `admin`)
- **Inheritance** — Groups can inherit from other groups

### Key Commands

```
# Add a permission to a group
/lp group <group> permission set <permission> true

# Remove a permission from a group
/lp group <group> permission unset <permission>

# Add a player to a group
/lp user <player> parent set <group>

# Give a player a temporary rank
/lp user <player> parent addtemp <group> 7d

# Open the web editor
/lp editor
```

### Useful Permission Nodes (EssentialsX)

```
essentials.fly              # /fly
essentials.gamemode         # /gamemode
essentials.tp               # /tp
essentials.tpa              # /tpa
essentials.home             # /home
essentials.sethome          # /sethome
essentials.home.multiple.vip # Multiple homes for VIP
essentials.kit.<kitname>    # Access specific kit
essentials.warp             # /warp
essentials.setwarp          # /setwarp (admin)
```

---

## 9. Setting Up Ranks & Groups

### Recommended Rank Structure

```
default  →  vip  →  vip+  →  mvp  →  mvp+  →  mod  →  admin  →  owner
```

### Creating Groups in LuckPerms

```
# Create groups
/lp creategroup default
/lp creategroup vip
/lp creategroup admin

# Set inheritance (vip inherits default permissions)
/lp group vip parent set default

# Set chat prefix (requires EssentialsX Chat and Vault)
/lp group vip meta setprefix "&6[VIP] "
/lp group admin meta setprefix "&c[Admin] "

# Set sort weight (higher = displayed higher in TAB)
/lp group vip setweight 50
/lp group admin setweight 90
```

### EssentialsX Chat Format

In `plugins/Essentials/config.yml`:

```yaml
chat:
  format: "&7[{DISPLAYNAME}&7] &f{MESSAGE}"
  # With LuckPerms prefix/suffix:
  format: "{PREFIX}&f{DISPLAYNAME}{SUFFIX}&7: &f{MESSAGE}"
```

---

## 10. Economy Setup

### Setting Up EssentialsX Economy

In `plugins/Essentials/config.yml`:

```yaml
# Starting balance for new players
starting-balance: 100

# Currency name
currency-symbol: "$"
currency-symbol-suffix: false
min-money: -10000  # Minimum balance (set to 0 to prevent debt)
max-money: 1000000000000  # Maximum balance
```

### Basic Economy Commands

```
/eco give <player> <amount>   # Give money (admin)
/eco take <player> <amount>   # Take money (admin)
/eco set <player> <amount>    # Set balance (admin)
/bal                          # Check your balance
/pay <player> <amount>        # Pay another player
/baltop                       # See richest players
```

### Setting Up Player Chest Shops (QuickShop Hikari)

1. Place a chest
2. Hold the item you want to sell
3. Left-click the chest
4. Type the price in chat
5. Done! Players can right-click to buy

---

## 11. Anti-Cheat & Security

### Grim Anticheat Setup

After installing Grim, the default config works well for most servers. Key settings in `config.yml`:

```yaml
# Toggle checks
checks:
  movement:
    speed: true
    fly: true
    nofall: true
  combat:
    killaura: true
    reach: true
  
# Punishment (commands run on violation threshold)
punishments:
  - "/warn %player% You have been flagged for cheating"
  - "/kick %player% Please do not use hacks"
```

### Server Security Checklist

- [ ] Change RCON password to something strong (or disable RCON if unused)
- [ ] Enable `whitelist` for private servers
- [ ] Install **CoreProtect** to log block changes and rollback grief
- [ ] Use **AuthMe** if running an offline/cracked server
- [ ] Keep plugins updated regularly
- [ ] Never share your `ops.json` file or server files publicly
- [ ] Use `online-mode=true` unless running a cracked server (prevents account spoofing)
- [ ] Set a strong password for your hosting panel

### Whitelist Management

```
/whitelist on             # Enable whitelist
/whitelist add <player>   # Add player
/whitelist remove <player>
/whitelist list
```

---

## 12. Performance Optimization

### RAM Allocation

Set JVM startup flags for best performance. Use **Aikar's Flags**:

```bash
java -Xms4G -Xmx4G \
  -XX:+UseG1GC \
  -XX:+ParallelRefProcEnabled \
  -XX:MaxGCPauseMillis=200 \
  -XX:+UnlockExperimentalVMOptions \
  -XX:+DisableExplicitGC \
  -XX:+AlwaysPreTouch \
  -XX:G1NewSizePercent=30 \
  -XX:G1MaxNewSizePercent=40 \
  -XX:G1HeapRegionSize=8M \
  -XX:G1ReservePercent=20 \
  -XX:G1HeapWastePercent=5 \
  -XX:G1MixedGCCountTarget=4 \
  -XX:InitiatingHeapOccupancyPercent=15 \
  -XX:G1MixedGCLiveThresholdPercent=90 \
  -XX:G1RSetUpdatingPauseTimePercent=5 \
  -XX:SurvivorRatio=32 \
  -XX:+PerfDisableSharedMem \
  -XX:MaxTenuringThreshold=1 \
  -Dusing.aikars.flags=https://mcflags.emc.gs \
  -Daikars.new.flags=true \
  -jar paper.jar --nogui
```

> **Note:** Set `-Xms` and `-Xmx` to the same value. Don't use more than 12GB even if you have more RAM — Java GC issues arise.

### TPS (Ticks Per Second)

Your server should run at **20 TPS**. Use `/tps` or the **spark** plugin to monitor.

Common causes of low TPS:
- Too many entities (use `/paper entity` to check)
- Too many hoppers
- Unoptimized redstone
- Plugin conflicts
- World size too large without pre-generation

### Recommended Performance Settings

In `bukkit.yml`:
```yaml
spawn-limits:
  monsters: 50      # Default: 70
  animals: 8        # Default: 10
  water-animals: 3  # Default: 5
  water-ambient: 10 # Default: 20
chunk-gc:
  period-in-ticks: 600
```

---

## 13. Backups

**Always back up your server.** Never rely on a single copy.

### What to Back Up

- `/world/` — Main overworld
- `/world_nether/` — Nether dimension
- `/world_the_end/` — The End dimension
- `/plugins/` — All plugin data and configs
- `server.properties`
- `ops.json`, `whitelist.json`, `banned-players.json`, `banned-ips.json`

### Automatic Backups with DriveBackupV2

A plugin that automatically backs up your server to Google Drive or Dropbox.

1. Install **DriveBackupV2**
2. Connect your Google Drive account via the setup link
3. Configure backup interval in `config.yml`:

```yaml
backup-storage-location: "DriveBackupV2"
delay: 1440           # Backup every 1440 minutes (24 hours)
keep-count: 7         # Keep 7 backups (one week)

backups:
  - type: "localDirectory"
    path: "world"
  - type: "localDirectory"
    path: "plugins"
```

### Manual Backup (via panel or FTP)

Most hosting panels (Pterodactyl, Multicraft, etc.) have a **Backup** button. Use it before any major changes.

---

## 14. Connecting Players & Networking

### Port Forwarding (Self-Hosted)

If hosting at home, you need to forward port **25565** (default) on your router:

1. Find your router's admin page (usually `192.168.1.1`)
2. Go to Port Forwarding
3. Forward TCP+UDP port **25565** to your local machine's IP
4. Share your **public IP** with players (find it at [whatismyip.com](https://whatismyip.com))

### Using playit.gg (No Port Forward Required)

[playit.gg](https://playit.gg) is a free tunnel that gives you a public address without exposing your real IP or needing router access.

1. Create an account and download the agent
2. Run the agent on your server machine
3. Claim your tunnel address and share it with players

### BungeeCord / Velocity (Multi-Server Networks)

For running multiple servers as a network (Lobby → Survival → Skyblock, etc.):

- **Velocity** — Recommended modern proxy (better performance and security)
- **BungeeCord** — Classic, widely supported
- **Waterfall** — Fork of BungeeCord with patches (less maintained now)

Basic Velocity setup:
1. Download Velocity
2. Add your backend servers to `velocity.toml`
3. Install **spark** and **LuckPerms** on the proxy
4. Set `online-mode=false` on all backend servers
5. Enable IP forwarding in paper.yml on backends

---

## 15. Moderation Tools

### Admin Commands (EssentialsX)

```
/ban <player> [reason]         # Permanently ban
/tempban <player> 7d [reason]  # Temporary ban
/kick <player> [reason]        # Kick from server
/mute <player>                 # Mute in chat
/unmute <player>
/vanish                        # Go invisible to players
/god                           # Enable godmode
/invsee <player>               # View player inventory
/sudo <player> <command>       # Run command as player
/tp <player>                   # Teleport to player
/tphere <player>               # Bring player to you
```

### CoreProtect Block Logging

```
/co inspect           # Toggle inspect mode — click a block to see its history
/co lookup u:<player> t:1h  # See everything a player did in the last hour
/co rollback u:<player> t:1h  # Rollback a griefer's changes
/co restore u:<player> t:1h   # Restore removed blocks from a player
```

### Recommended Staff Rank Setup

| Rank | Permissions |
|------|-------------|
| **Helper** | Basic moderation: /mute, /kick, /warn |
| **Moderator** | + /ban, /tempban, /vanish, /invsee, CoreProtect inspect |
| **Senior Mod** | + /ban-ip, rollbacks, access to all worlds |
| **Admin** | + Plugin management, config access, /op |
| **Owner** | Full access |

---

## 16. Common Issues & Troubleshooting

### Server Won't Start
- Check your Java version. Minecraft 1.17+ requires **Java 17+**, 1.20+ works best with **Java 21**
- Check `latest.log` in the `/logs/` folder for error messages
- Make sure no other program is using port 25565

### Players Can't Connect
- Verify port forwarding is correct (self-hosted)
- Check `server.properties` — confirm `server-port=25565`
- Ensure `online-mode=true/false` matches whether you're using premium accounts
- Try `telnet <your-ip> 25565` to test connectivity

### Server is Lagging (Low TPS)
1. Install **spark** and run `/spark tps`
2. Run `/spark profiler start` for 30 seconds, then `/spark profiler stop`
3. Check the report for what's causing lag
4. Common fixes: reduce view-distance, reduce mob limits, pre-generate chunks

### Plugin Errors / Conflicts
- Read `latest.log` — errors show which plugin is failing
- Disable plugins one by one to isolate the conflict
- Make sure all plugins are compatible with your server version
- Check if the plugin requires dependencies (like Vault, PlaceholderAPI)

### Players Getting Kicked for "Flying"
- EssentialsX `/fly` and Grim can conflict on some servers
- Add your anticheat plugin to EssentialsX's bypass list, or adjust Grim's check sensitivity

---

## 17. Tips & Best Practices

### Before Launch Checklist
- [ ] Server software installed and updated
- [ ] Essential plugins installed (EssentialsX, LuckPerms, Vault)
- [ ] Spawn area built and `/setspawn` configured
- [ ] World border set
- [ ] World pre-generated with Chunky
- [ ] Permissions configured for at least `default`, `vip`, and `admin` groups
- [ ] Anti-cheat installed and configured
- [ ] CoreProtect installed for logging
- [ ] Backup system in place
- [ ] MOTD set in `server.properties`
- [ ] Server rules created (consider a `/rules` command or sign board at spawn)

### General Advice

- **Test everything as a regular player** — Create an alt account or use `/lp user <alt> parent set default` to test the default player experience
- **Don't over-plugin** — More plugins = more potential conflicts and lag. Only install what you need
- **Keep plugins updated** — Outdated plugins are a security risk and may have known exploits
- **Communicate with your players** — Use DiscordSRV to bridge your Minecraft and Discord communities
- **Monitor your logs** — Check `logs/latest.log` regularly for errors and suspicious activity
- **Never `/op` random players** — Op gives full access to everything including file system commands

### Useful Websites

| Resource | URL |
|----------|-----|
| Paper Downloads | https://papermc.io/downloads |
| SpigotMC Plugin Repository | https://www.spigotmc.org/resources/ |
| Hangar (Paper plugin hub) | https://hangar.papermc.io |
| Modrinth (Plugins & Mods) | https://modrinth.com |
| LuckPerms Docs | https://luckperms.net/wiki/Home |
| EssentialsX Docs | https://essentialsx.net/wiki/Home.html |
| PlaceholderAPI Placeholders | https://github.com/PlaceholderAPI/PlaceholderAPI/wiki/Placeholders |
| Minecraft Server Comparison | https://mcstatus.io |
| Aikar's JVM Flags | https://aikar.co/2018/07/02/tuning-the-jvm-g1gc-garbage-collector-flags-for-minecraft/ |

---

*Guide version 2.0 — Last updated 2025*
