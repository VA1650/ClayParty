# 💎 ClayParty: Dynamic Instance-Based Mini-Game

![Version](https://img.shields.io/badge/Version-1.12.2-blue.svg)
![Type](https://img.shields.io/badge/Architecture-Instance--Based-orange.svg)
![Status](https://img.shields.io/badge/Status-Production--Ready-brightgreen.svg)

**ClayParty** is a high-performance Spigot plugin (1.12.2) implementing BlockParty mechanics using a dynamic world containerization system. The plugin automatically manages arena instances, ensuring complete player isolation and zero load on the main world.

---

## 🚀 Key Features

* **Instance Deployment:** Automatic world cloning from templates (`template_...`) into active instances (`run_...`).
* **Zero-Conflict System:** Supports an unlimited number of concurrent arenas without coordinate overlapping.
* **Advanced Field Generation:** 32x32 field generation based on a 16x16 logic grid with support for special modes:
    * `Border Mode` — find the border between two colors.
    * `Double Color` — two safe colors simultaneously.
    * `Ice Floor` — slippery flooring for increased difficulty.
* **Smart Cleanup:** Full decommissioning of temporary worlds upon game completion to save disk space.

---

## 🛠 Commands & Permissions

| Command | Description | Permission |
| :--- | :--- | :--- |
| `/bp create <type>` | Create a new instance (aqua, space, desert) | `clayparty.admin` |
| `/bp join <id>` | Join a specific arena | `clayparty.player` |
| `/bp start` | Manually start rounds on the current arena | `clayparty.admin` |
| `/bp list` | List all active instances | `clayparty.player` |

---

## 📁 Installation & Structure

1. Place `ClayParty.jar` into the `plugins` folder.
2. Create template folders in the server root directory:
   * `template_aqua`
   * `template_space`
   * `template_desert`
3. Ensure the platform in the templates is located at the coordinates specified in the config.

---

## 🧠 Technical Architecture

The project is built on principles of **Utility-First Personalization** and strict data typing:
* **FieldManager:** Encapsulates block rendering logic using `DyeData` for 1.12.2.
* **ArenaManager:** Manages world lifecycles and the active session pool.
* **Async Logic:** All timers and calculations are handled via `BukkitRunnable` to prevent main thread lag.

---

> Built with ❤️ by Annie312
