# QuickCast PvP

**QuickCast PvP** is a lightweight **client-side Fabric mod** for **Minecraft Java 1.21.1** that lets you instantly quick-use PvP items/actions with a **middle mouse click** — then (by default) **restores your previous hotbar slot** for smooth combos.

🔗 GitHub: https://github.com/modclaim/QuickCast-PvP

---

## ✨ Features

- **Middle-click QuickCast**
  - **Ender Pearl** — quick throw/use
  - **Wind Charge** — quick use/throw
  - **End Crystal** — attempt placement at crosshair (server-validated)
- **Fast hotbar search (0..8)**  
  Temporary switch → use/place → restore (default)
- **After-use behavior**
  - `RESTORE` (default) — return to previous slot
  - `KEEP_NEW_SLOT` — stay on the used item slot
- **Cooldown protection** (default `120ms`) to prevent spam
- Optional **chat feedback**
- Optional **allowWhileScreenOpen** (use while inventory/menu is open)
- **Mod Menu integration** + **Cloth Config** config screen (optional)
- Minimal overhead (reacts only on input; no heavy tick spam)

---

## 🎮 How to Use

1. Put your desired item in the **hotbar**:
   - Ender Pearl / Wind Charge / End Crystal
2. Press **Middle Mouse Button**
3. The mod:
   - finds the item in hotbar
   - temporarily switches to that slot
   - triggers use/place
   - restores your previous slot (default)

> If the item is not found, nothing happens (or optional chat feedback).

---

## ⚙️ Configuration

Config file is saved at:

- `.minecraft/config/quickcastpvp.json`

### Options

- `defaultAction`: `ENDER_PEARL | WIND_CHARGE | END_CRYSTAL`
- `afterUseBehavior`: `RESTORE | KEEP_NEW_SLOT`
- `requireHotbarOnly`: `true/false`
  - **v1.0.0 note:** `requireHotbarOnly=false` (inventory swap) is **not implemented yet** — it will fall back to hotbar-only.
- `restorePreviousSlot`: `true/false`
- `cooldownMs`: integer (default `120`)
- `showChatFeedback`: `true/false`
- `allowWhileScreenOpen`: `true/false`
- `crystalPlaceMode`: `TRY_PLACE | PLACE_AT_CROSSHAIR_IF_POSSIBLE`

### Mod Menu + Cloth Config (recommended)
If you install:
- **Mod Menu**
- **Cloth Config**

…you will get an **in-game config screen**.

---

## 📦 Installation

### Requirements
- **Minecraft Java 1.21.1**
- **Fabric Loader**
- **Fabric API** (required)

### Steps
1. Install Fabric Loader for **1.21.1**
2. Download:
   - **Fabric API**
   - `quickcastpvp-*.jar` from **Releases**
3. Put both `.jar` files into your mods folder:

**Windows:**
`%appdata%\.minecraft\mods`

**Linux:**
`~/.minecraft/mods`

**macOS:**
`~/Library/Application Support/minecraft/mods`

---

## ✅ Compatibility
- Minecraft: **1.21.1**
- Loader: **Fabric**
- Environment: **Client-side**

---

## 🧠 Notes / Known Issues

- **End Crystal placement** is always **server-validated** (obsidian/bedrock, free space, etc.). The mod only attempts to place.
- `requireHotbarOnly=false` inventory-to-hotbar swapping is **TODO** for a future version.

---

## 🛠️ Development

### Build
```bash
./gradlew build
