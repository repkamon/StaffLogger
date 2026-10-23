[![BuiltByBit](https://img.shields.io/badge/BuiltByBit-Get%20Pre--built%20Jar-blue)](https://builtbybit.com/resources/stafflogger-staff-audit-anti-abuse.126230/)

# 🛡️ StaffLogger

**Enterprise-Grade Staff Auditing & Anti-Abuse Security Suite for Minecraft Networks**

StaffLogger delivers deep, real-time visibility into administrative activities, staff communications, and permission escalation. Built with native Java 21 asynchronous I/O, it ensures your server maintains 20 TPS without main-thread blocking.

---

## ✨ Features

* **⚡ Native Async Pipeline:** Utilizes Java 21 `HttpClient` for non-blocking Discord webhook dispatches.
* **🚨 Threat Escalation Engine:** Color-coded severity tiers with critical role mentions for commands like `/op`, `/stop`, and `/lp`.
* **📦 Creative Exploit Watchdog:** Tracks illegal item duplication (middle-click cloning), container transfers, and drops.
* **🎒 Inventory Delta Snapshots:** Automatically compares inventories before and after Creative mode, logging every spawned item.
* **🧨 Griefing & Sabotage Defense:** Intercepts unauthorized placements of TNT, lava, crystals, and respawn anchors.
* **🕵️ Session & Whisper Auditing:** Tracks join/quit durations, IP records, and monitors whispers (`/msg`, `/tell`, `/w`).
* **💾 Embedded SQLite Fallback:** Local logging ensures zero data loss during Discord downtime, viewable directly in-game.

---

## 🚀 Installation

1. Stop your Minecraft server.
2. Place `StaffLogger.jar` into your server's `plugins/` directory.
3. Start the server to generate default configurations.
4. Open `plugins/StaffLogger/config.yml` and paste your Discord Webhook URLs.
5. Set your Discord Alert Role ID in `Settings.Alert-Role-ID` for ping notifications.
6. Run `/stafflogger reload` in-game or via console.

---

## ⌨️ Commands & Permissions

| Command | Permission | Description |
| :--- | :--- | :--- |
| `/stafflogger reload` | `stafflogger.admin` | Hot-reloads configuration files. |
| `/stafflogger lookup <player>` | `stafflogger.admin` | Queries the local SQLite database for past staff actions. |
| *Passive Monitoring* | `stafflogger.log` | Any staff member with this node is monitored. |

---

## ⚙️ Configuration (`config.yml`)

```yaml
Webhooks:
  Default: "[https://discord.com/api/webhooks/YOUR_GENERAL_WEBHOOK](https://discord.com/api/webhooks/YOUR_GENERAL_WEBHOOK)"
  Punishments: "[https://discord.com/api/webhooks/YOUR_PUNISHMENT_WEBHOOK](https://discord.com/api/webhooks/YOUR_PUNISHMENT_WEBHOOK)"

Settings:
  Enable-Gamemode-Log: true
  Enable-Command-Log: true
  Enable-Item-Abuse-Log: true
  Enable-Grief-Log: true
  Enable-Session-Log: true
  Enable-Chat-Snoop: true
  Alert-Role-ID: "123456789012345678"

Punishment-Commands:
  - "/ban"
  - "/tempban"
  - "/kick"
  - "/mute"
  - "/tempmute"
  - "/unban"


🛠️ Requirements

* **Platform:** Paper, Purpur, Spigot (Supports 1.16.5 through 1.21+ and newer)
* **Java:** Java 21

Database: SQLite (Embedded, no separate setup required)

Developed by repkamon. Support available on official channels.
