# Gludio Gate — Auto Leveling Script Maker for the Adrenaline Bot (Lineage 2 High Five)

[![Latest version](https://img.shields.io/github/v/release/sakahex/Gludio-Gate?label=latest%20version&color=2ea44f&style=for-the-badge)](https://github.com/sakahex/Gludio-Gate/releases/latest)
[![Download](https://img.shields.io/badge/download-GludioGateSetup.exe-0969da?style=for-the-badge&logo=windows)](https://github.com/sakahex/Gludio-Gate/releases/latest/download/GludioGateSetup.exe)

**Gludio Gate builds your own automatic leveling for the Adrenaline bot (L2 / Lineage 2 High Five, Hi5) — for any levels you want, with no scripting.**

Set up your zones once and your character levels by itself: it teleports, buys gear and supplies, does quests,
walks to the right farm spot and moves on when it levels up. Everything is done with clicks in a modern Windows app.

💬 **[Join our Discord](https://discord.gg/PUMUGWgAkY)** for help, news and zone packs.
📖 **[Step-by-step manual](MANUAL.md)** — from install to a character that levels by itself.
🗺️ **[Geodata](Geodata)** — download for **Auto route** on the route map.

![Gludio Gate - Lineage 2 auto leveling editor for the Adrenaline bot](screenshots/main.png)

> Adrenaline does the **fighting** (skills, buffs, potions, pick up).
> Gludio Gate decides **where to go and what to buy** — and moves on by itself.

---

## ✨ What it does

- 🗺️ **Zones for any levels** — up to 100 zones; several steps per level range (e.g. *shop in Giran → farm at Ant Nest*).
- 🧭 **One trip list per zone** — teleport → shops, gatekeepers, buffers and quests in **your** order → farm spot. Move anything with ↑ ↓, remove with ✕.
- 📜 **Quests** — talk steps (accept, deliver, turn in) and hunt steps (collect quest items at the farm spot). *Add this quest* even makes the walking routes between the quest NPCs. Each character keeps its own progress and **goes on where it stopped** after a restart.
- 🛒 **Shops** — pick items straight from **what the merchant sells** (grade, type, price, icons). Gear is bought once and worn.
- 🧪 **Supplies** — one shop for potions, soulshots and scrolls at every level. Running low while farming → scroll to town, restock, back to farming. Soulshot grades switch by level by themselves. **Sell junk** at every shop visit.
- ✨ **Buff stops** — buy buffs from players or NPC buffers; skipped when all buffs are still on. *Add my target* adds the buff seller you target in game.
- 🎥 **Routes** — press **Record** and walk in game, draw them on the **real game map**, or let **Auto route** find the way.
- 🛡️ **Safe** — stuck check, retries when a gatekeeper fails, finishes the fight before teleporting, never wastes a Scroll of Escape in town.
- 📊 **Stats and alerts** — level, exp/hour and adena charts per character, zone stats, and an alert when a character dies or stops moving.
- ✉️ **Mail** — takes your in-game mail for you.
- 👥 **Several characters** at once, **several scripts** (e.g. one for mages), **zone packs** to share setups.
- 🔎 **Game database** — find any item, NPC or skill with its id and icon.
- 🌍 **5 languages**, dark and light theme. 🔄 **Updates itself** — click *Yes* and it's done.

---

## 🧭 How it works

**1. Build the trip for each level range** — in the order the character should do it:

![A zone's trip: teleport, shops and farm spot](screenshots/main.png)

**2. Add quests right into the trip** — each character's progress is saved, a restart goes on where it stopped:

![Quest steps: talk to an NPC, hunt quest items](screenshots/quest.png)

**3. Record, draw or auto-route the paths on the real game map:**

![Route map with a walking route in Ant Nest](screenshots/map.png)

**4. Shopping lists from what the merchant really sells:**

<img src="screenshots/picker.png" width="640" alt="Pick items from what the merchant sells">

**5. One Supplies shop for every level** — the character restocks by itself when it runs low:

![Supplies: potions, soulshots and scrolls per level](screenshots/supplies.png)

**6. Run** `Leveling_1_40.txt` in Adrenaline — the top bar shows what the character is doing, with live stats.

<img src="screenshots/settings.png" width="640" alt="Gludio Gate settings">

*Settings — sensible defaults, change them only if you want to.*

<img src="screenshots/database.png" width="640" alt="Lineage 2 game database: items, NPCs, skills with ids">

*Game database — every item, NPC and skill with its id.*

---

## 📥 Install

1. Download **[GludioGateSetup.exe](https://github.com/sakahex/Gludio-Gate/releases/latest/download/GludioGateSetup.exe)** — always the latest version.
2. Run it and select your **Adrenaline folder** (the one that contains `Scripts`).
3. Start **Gludio Gate** from the desktop shortcut.

<img src="screenshots/setup.png" width="480" alt="Gludio Gate installer">

> *"Windows protected your PC"*? Click **More info → Run anyway** — the program is new, not harmful.

**Needs:** Windows 10/11 · Adrenaline · a Lineage 2 **High Five** server · a license key.

### 🔑 Activation

On first start the editor shows your **machine code** → **Copy** → send it to the seller → paste the **license key** you get → **Activate**.
One key works on one PC; a new PC or a Windows reinstall needs a new key.

### ▶️ Start leveling

1. Log in your character and set up fighting in Adrenaline as usual.
2. In Adrenaline run **`Scripts\Leveling\Gludio Gate\Leveling_1_40.txt`**.
3. Open Gludio Gate to build and change your zones, then press **💾 Save** — the characters running that script use the changes right away.

New to it? Follow the **[step-by-step manual](MANUAL.md)**.

---

## 🗺️ Auto route (geodata)

Don't want to walk and record every route? The route map's **Auto route** button finds a walkable way
between your points by itself — around walls, over bridges, up stairs. For that it needs the game's
**geodata** (the map of where you can walk):

1. Download **[Geodata_HighFive_L2J.zip](https://github.com/sakahex/Gludio-Gate/releases/download/geodata-hi5/Geodata_HighFive_L2J.zip)** (about 220 MB) and unzip it anywhere, e.g. `Desktop\Geodata`.
2. Gludio Gate → **Settings → App → Geodata folder** → pick that folder.
3. Open a route's **Map** → **Auto route**. Check it on the map and fix points by hand if you like.

Only the editor uses these files — Adrenaline doesn't need them. You do this once — updates keep your geodata folder.
*The geodata is the public [L2J_Geodata_Hi5](https://github.com/Zyno/L2J_Geodata_Hi5) project (GNU GPL v3).*

---

## 🔄 Updates

The editor checks for a new version when it starts — click **Yes** and it updates itself and the scripts.
Your zones and settings are never overwritten.

---

## ❓ FAQ

**What is Gludio Gate?**
A Windows editor that makes auto leveling scripts for the **Adrenaline bot** in **Lineage 2 High Five**: zones, shops, quests, buffs, supplies and routes — without writing code.

**Does it replace Adrenaline?**
No. Adrenaline still does the fighting. Gludio Gate's script tells it where to go, what to buy and when to move on.

**Which servers does it work on?**
Lineage 2 **High Five (Hi5)** servers that you play with Adrenaline.

**Can it level from 1 to 85?**
Yes — you set the zones for any level ranges you want, up to 100 zones per script.

**Where do I get help?**
On **[our Discord](https://discord.gg/PUMUGWgAkY)**. When something goes wrong, post the red lines from Adrenaline's log.

---

<sub>Keywords: Lineage 2 bot, L2 Adrenaline bot script, Adrenaline auto leveling, L2 High Five leveling script, Hi5 auto farm, L2Toggle, Adrenaline script maker, L2 bot 1-85.</sub>
