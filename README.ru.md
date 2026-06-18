# 💎 ClayParty: Dynamic Instance-Based Mini-Game

![Version](https://img.shields.io/badge/Version-1.12.2-blue.svg)
![Type](https://img.shields.io/badge/Architecture-Instance--Based-orange.svg)
![Status](https://img.shields.io/badge/Status-Production--Ready-brightgreen.svg)

**ClayParty** — это высокотехнологичный плагин для Spigot (1.12.2), реализующий механику BlockParty с использованием системы динамической контейнеризации игровых миров. Плагин автоматически управляет инстансами арен, обеспечивая полную изоляцию игроков и нулевую нагрузку на основной мир.

---

## 🚀 Key Features

*   **Instance Deployment:** Автоматическое клонирование миров из шаблонов (`template_...`) в оперативные инстансы (`run_...`).
*   **Zero-Conflict System:** Неограниченное количество арен запускается одновременно без пересечения координат.
*   **Advanced Field Generation:** Генерация поля 32x32 на базе 16x16 логической сетки с поддержкой спец-режимов:
    *   `Border Mode` — поиск границы между двумя цветами.
    *   `Double Color` — два безопасных цвета одновременно.
    *   `Ice Floor` — скользкий пол для повышенной сложности.
*   **Smart Cleanup:** Полная декоммиссия временных миров после завершения игры для экономии дискового пространства.

---

## 🛠 Commands & Permissions

| Command | Description | Permission |
| :--- | :--- | :--- |
| `/bp create <type>` | Создать новый инстанс (aqua, space, desert) | `clayparty.admin` |
| `/bp join <id>` | Присоединиться к конкретной арене | `clayparty.player` |
| `/bp start` | Ручной запуск раундов на текущей арене | `clayparty.admin` |
| `/bp list` | Список всех активных инстансов | `clayparty.player` |

---

## 📁 Installation & Structure

1. Поместите `ClayParty.jar` в папку `plugins`.
2. В корневом каталоге сервера создайте папки-шаблоны:
   * `template_aqua`
   * `template_space`
   * `template_desert`
3. Убедитесь, что в шаблонах платформа находится по координатам, указанным в конфиге.

---

## 🧠 Technical Architecture

Проект построен на принципах **Utility-First Personalization** и строгой типизации данных:
*   **FieldManager:** Инкапсулирует логику рендеринга блоков через `DyeData` для 1.12.2.
*   **ArenaManager:** Управляет жизненным циклом миров и пулом активных сессий.
*   **Async Logic:** Все таймеры и расчеты вынесены в `BukkitRunnable` для предотвращения лагов основного потока.

---

> Built with ❤️ by Annie312
