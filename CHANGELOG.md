# 🆕 Gludio Gate — what's new

Every change since **3.0.0**, for players. The editor updates itself (click **Yes** when it asks) and updates
all your leveling scripts with it — your zones and settings are never touched.
**After an update, restart your scripts in Adrenaline once.**

---

## 3.0.11 — October 2026

*3.0.1 – 3.0.10 were test builds and never released, so everything below is new in 3.0.11.*

### ⚡ Faster and steadier

- **Fast NPCs** — talking to NPCs, clicking their buttons, buying and selling no longer wait fixed pauses: each step goes on as soon as the game answered. A typical shop / gatekeeper / quest visit takes about 1–2 s instead of 5–6 s.
- **Less work for Adrenaline** — the leveling scripts no longer stay connected to Gludio Gate. Before, every character's connection ran all the time; the *Timer Error* / *Access violation* crashes in Adrenaline came with that work.
- **Running now** — the top of the editor shows which characters are leveling right now, live (each script only writes the time every 20 s; nothing is read from the game).
- **Connect on demand** — need the game buttons (Record, Nearby, Set NPC, Pick…)? Click the character in *Running now*. It connects within about 2 s and disconnects by itself 5 minutes after the last game button. `Editor.txt` is no longer needed for that.

### 🏕️ Safe zone (farm spot)

- On the farm spot's **Map**: **🛡 Set safe zone**, then click the map where it should be (drag it to move it, right-click → *Clear safe zone*).
- When a buff runs out while farming, the character **walks to the safe zone, kills whatever followed it, then does the rebuff trip**.
- Every part has a time limit (walk, standing still, fight). If it doesn't work out it falls back to the old way: Scroll of Escape, then the rebuff trip.
- Switch it on/off per farm spot with the checkbox on the map. No safe zone set = the bot keeps farming when the buffs run out, like before.

### 🗺️ Route map

- **Drag with the left mouse button** to move the map (when *Draw* is off); the next map squares load as you go.
- **Center on character** button.
- Uses less memory on big maps.

### ✨ Buffs

- A **buffs step is skipped as a whole** when the character already has all its buffs — no more *teleport to Giran and straight back to Gludio*.
- Switch it off per buff stop: *Skip the buffers when all buffs are still on*.

### ⚔️ Gear presets

- **Gear presets** — pick a class (dwarf, knight, dagger, archer, mage, …) and its **weapon and armor** go into your gear shops, from the merchants your script already has (no-grade / D / C).
- Shows **how much adena** a preset costs.
- *Save as a new script* with a preset → one script per player / class.
- Opening a script whose shops have no gear offers a preset.

### 👥 Party

- **Party** button — parties with a **leader**, members and their role (**Fighter / Healer**), for your own party scripts. Saved in the script's ini (`[Party1]` … `[Party5]`, the format is in `PARTY.txt`).
- Lists every character that ran a leveling script — no need to start `Editor.txt` on each one first.
- *Check my setup* warns about party problems (e.g. the leader is not one of its members, no safe zone for the party to regroup).

### 🧭 Zones

- **The zone list looks like the trip cards** — every level range is a header (*Lv 5-15*), its zones are numbered steps joined by a line, with a badge for what each step does: **FARM / BUFFS / SHOP / QUEST / WALK**.
- **Importing a zone pack** (e.g. one *Buffs* zone) into levels you already have: **Yes** now *adds* it as a step before your farm spot; replacing your zones is **No**. The farm spot always stays the last step.

### 🛡️ Fixes

- A character that was **already in game when Adrenaline started** (Adrenaline sees an empty bag) no longer travels and buys everything again — the log says to relog it, and it waits.
- **Item teleports** (e.g. *Scroll of Escape: Kamael Village*) right after the script starts no longer say *no item*, and a failed one no longer walks the routes from the wrong place.
- The **version** is shown in the title bar (before, About always said 3.0.0).

### 🧹 Removed

- **Stats, Alerts and the stats history**. **Zone stats** stay (button at the top).
- The *Game link* section in Settings (not needed any more).

---

## 3.0.0 — 17 October 2026

- Rebuilt as a modern Windows 11 style app (same features as 2.0.0).
- Quests: *Add this quest* makes the walking routes between the quest NPCs by itself (needs geodata).
- Mail button: takes your mail by clicking the game window for you.
- Buff stops: *Skip the buffers when all buffs are still on*; buffs the game names differently are recognised; *Add my target*.
- Fixed: dialog buttons with a double space in their text; reading the target while mobs die no longer risks an Adrenaline crash.

Older versions: see **[Releases](https://github.com/sakahex/Gludio-Gate/releases)**.

---

## ❓ L2 itself shows a *Critical Error*?

That is the game client, not Gludio Gate:

- *"The system file may have been damaged… (Bad name index …)"* while entering the world → a damaged client file: close the game and run your server's **updater / full file check**.
- A crash in **nvd3dum.dll** → the NVIDIA graphics driver: update or reinstall the driver; with many clients open, lower their graphics settings.

💬 **Help, news and zone packs: [our Discord](https://discord.gg/PUMUGWgAkY)**
