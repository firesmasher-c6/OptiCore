# 🚀 OptiCore | Build #10
> **The Ultimate High-Performance Engine for PurpurMC & Paper Servers.**
> *Current Build: 26.1.2*

---

## 💎 Core Features

### 🛡️ Smart System Protection
* **Main-Thread Optimizer:** A specialized MSPT-aware engine that handles entity cleanup safely. It uses a tick-buffer to prevent lag spikes while clearing entities in high-density regions.
* **Startup AI Generator:** Scans system hardware and the root directory to find your specific server JAR (Purpur, Paper, etc.) and generates the **perfect Aikar's Flags** custom-tailored to your RAM.
* **Health Monitoring:** Real-time tracking of TPS and MSPT with direct hardware integration.

### ⚙️ Optimization & Management
* **Plug & Play Logic:** Pre-tuned configurations for `spigot.yml`, `purpur.yml`, `paper-global.yml`, and `bukkit.yml` to maximize performance from the first boot.
* **Regional Chunk Tracker:** Identifies "hotspot" chunks with the most entities to find lag sources instantly. (Disabled by default).
* **Lightweight Anti-Cheat:** Minimal-impact security monitoring that alerts operators to suspicious activities without eating CPU cycles.

---

## ⌨️ Command Registry

| Command | Permission | Description |
| :--- | :--- | :--- |
| `/startup generate` | `admin.startup` | **NEW:** Scans hardware/JAR and generates an optimized `.txt` flag set. |
| `/oc reload` | `admin.opticore` | Reloads the core OptiCore engine and YAML configs. |
| `/oc purge` | `admin.opticore` | Manual emergency entity purge to free up server RAM. |
| `/chunks` | `admin.tracker` | View active chunks and entity counts per region. |
| `/chunktracker <on/off>` | `admin.tracker` | Toggles the heavy tracking engine to save CPU/RAM. |
| `/panel <player>` | `admin.features` | View player metadata (Coordinates, Playtime, Stats). |
| `/playerlist` | `op` | Check if players are connecting via Java or Bedrock. |
| `/networking` | `op` | Real-time ping (ms) check for all players. |
| `/tps` | `op` | High-accuracy system health display. |
| `/version` | `op` | Check Minecraft version, Software type, and OptiCore Build ID. |

---

## 📁 System Architecture

### 📂 `/plugins/OptiCore/`
* **`OptiCore.yml`**: The main configuration hub for toggling gamerules and engine settings.
* **`StartupGenerator/`**: Temporary storage for AI-generated startup flags (Auto-purges every 60s for security).
* **`Optimizers/`**: Configuration for MSPT thresholds and entity caps.
* **`platforms.yml`**: Database for Bedrock/Java UUID mapping (Geyser compatibility).
* **`system.yml` & `features.yml`**: Toggle switches for the Anti-Cheat and Player Analytics modules.

### 📜 Engine Scripts (`/plugins/skript/scripts/`)
* **`OptiCore.sk`**: The primary engine that syncs YAML settings to the live world.
* **`startupgenerator.sk`**: Handles hardware analysis and root-level JAR detection.
* **`system.sk`**: Lightweight security and operator broadcasting engine.
* **`tracker.sk`**: Regional monitoring and entity hotspot detection.

---