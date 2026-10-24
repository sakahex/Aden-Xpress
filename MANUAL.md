# 📖 Gludio Gate — Step-by-step manual

This guide takes you from a fresh install to a character that levels by itself.
New here? Read the steps **in order** — each one builds on the one before.

> **The one idea to remember:** Adrenaline does the **fighting** (skills, buffs, potions, pick up).
> Gludio Gate decides **where to go and what to buy** — teleport, shops, quests, farm spot — and moves on when the character levels up.

---

## Contents

1. [Before you start](#1-before-you-start)
2. [Install and activate](#2-install-and-activate)
3. [Connect the editor to the game](#3-connect-the-editor-to-the-game)
4. [A tour of the window](#4-a-tour-of-the-window)
5. [Make your first zone](#5-make-your-first-zone)
6. [Build the trip](#6-build-the-trip)
7. [Record routes](#7-record-routes)
8. [Shops](#8-shops)
9. [Quests](#9-quests)
10. [Shopping list (gear and supplies)](#10-shopping-list-gear-and-supplies)
11. [Check and run](#11-check-and-run)
12. [Settings](#12-settings)
13. [More tools](#13-more-tools)
14. [Tips for a trip that never gets stuck](#14-tips-for-a-trip-that-never-gets-stuck)
15. [Problems and fixes](#15-problems-and-fixes)

---

## 1. Before you start

You need:

- Windows 10 or 11
- **Adrenaline** bot, with a working config for your character (attack, skills, buffs, potions, pick up)
- a Lineage 2 **High Five** server
- a Gludio Gate license key

First make sure your character **fights well in Adrenaline on its own** — stand it in a farm zone and turn the bot on.
Gludio Gate never changes how it fights; it only takes it to the right places.

---

## 2. Install and activate

1. Go to **[Releases](../../releases)** → newest version → download **`GludioGateSetup.exe`**.
2. Run it and pick your **Adrenaline folder** (the one that contains `Scripts`).
   Gludio Gate installs into `Adrenaline\Scripts\Leveling\Gludio Gate`.
3. Start **Gludio Gate** (desktop shortcut).
4. The first time, it shows your **machine code** → click **Copy** → send it to the seller → paste the **license key** you get → **Activate**.

> *"Windows protected your PC"*? Click **More info → Run anyway**.
> One key works on one PC. New PC or Windows reinstall = new machine code = ask for a new key.

After activation the scripts appear next to the program:

| File | What it is |
|---|---|
| `Leveling_1_40.txt` | **the leveling script — the one you run in Adrenaline** |
| `Editor.txt` | connects the editor to the game *without* leveling (for recording routes) |
| `Leveling_1_40.ini` | your zones, shops, routes and settings (saved when you press **Save**, never overwritten by updates) |
| `EditorLink.txt`, `SettingsModule.txt`, `PathRecorder.txt` | helpers the scripts need — leave them there |

---

## 3. Connect the editor to the game

The editor needs the game only for the **game buttons** (Record, Nearby, Set from my target, Pick…).
Building zones, shops and quests works without it.

1. Log your character in and start **`Leveling_1_40.txt`** in Adrenaline (or **`Editor.txt`** — only connects, no leveling).
2. The character appears in **Running now** at the top of Gludio Gate.
3. **Click its name** — within about 2 s the top bar turns green: **Lv 23 · Target: …**.
   It stays connected until 5 minutes after the last game button, then disconnects by itself.

The leveling script never stays connected on its own — so leveling puts no extra work on Adrenaline.
Several characters can run at once; click the one you want to use the game buttons with.

---

## 4. A tour of the window

**Top bar** — the connected character's level and target, **Running now** (every character that is leveling — click one to connect it), the version and your license.
Buttons: **Recorder**, **Database**, **Nearby**, **Settings**.

**Menu row**

| | |
|---|---|
| **Recorder** | advanced route recorder |
| **Game database** | look up items, NPCs, skills and game messages with their ids |
| **Check for updates** | download the newest version |
| ⚙ **Settings** | bot timings, escape scroll, theme, language, folders ([section 12](#12-settings)) |
| **License key… / About** | your key, version and what's new |

**Left side**

- **Script** — the script you're editing: pick another one in the box. The **…** next to it: new script, save as a copy, open from another folder, rename, delete.
  Under it: which characters run this script right now, and **💾 Save** / **Undo changes**.
  Your changes reach the running characters only when you press **Save** — to try something on one character, use *… → Save as a new script* and run that copy on it.
- **Character buttons** (2+ characters online) — show the script each one runs; click one to edit its script.
- **Zones** — your zones grouped by level range (*Lv 5-15*). Each zone is a numbered step with a badge: **FARM** (the last step, where the bot fights), **BUFFS**, **SHOP**, **QUEST** or **WALK**. Click one to edit it.
- **▲ Up / ▼ Down** — order of zones that start at the same level.
- **+ Add zone / Delete zone**
- **🛒 Shopping list** — gear and supplies for every level, by town ([section 10](#10-shopping-list-gear-and-supplies)).
- **Zone packs** — export / import zones with all their routes.

**Right side** — the selected zone: its name, levels and **the trip**.

Press **💾 Save** (or Ctrl+S) under the script name when you're done - only then the characters that run the script use your changes. *● not saved* shows there is something to save; **Undo changes** goes back to the last save. Hover any **(?)** for help, click **More ▾** on a card for rarely used options.

---

## 5. Make your first zone

> 🧙 **Quick start:** script **…** menu → **New script with the start wizard…**. Pick the levels (e.g. 1 to 40),
> one zone every N levels, a class gear preset, and soulshots / Scrolls of Escape / potions. It makes the zones and
> a filled shopping list (the shops of Gludio and Giran). Then you only record each zone's farm spot and, in the
> shopping list, the walk from each town's teleport to its shop NPCs — and press **Save**.

1. Click **+ Add zone → New zone (the next levels)**.
2. Type a **Name** (e.g. *Ant Nest*) and the **Levels**, e.g. **20** to **30**.

**How levels work:** a zone is used **from the first level until the character reaches the second one**.
*20 to 30* = levels 20–29; at level 30 the next zone takes over. (So *5 to 5* would never be used!)

**Several steps for the same levels** — e.g. *shop in Giran*, then *farm at Ant Nest*:
**+ Add zone → Another step for the same levels**. Steps run top to bottom and the bot **farms at the last one**.
The earlier steps are "pass-through" (shopping, gatekeepers…).

> 💡 Zones whose levels overlap but differ (e.g. *Cruma 35–45* and *C-grade shopping 40–45*) are done together;
> a zone without a farm spot (pure shopping) is always done **first**, in town.

---

## 6. Build the trip

The trip is everything the character does to get to its farm spot, **top to bottom**:

```
THE TRIP, IN THIS ORDER                          [+ Add ▾]
 1 TELEPORT   .giran                                    ✕
 2 SHOP       Helvetia                       ▲ ▼        ✕
 3 QUEST      Head for the Hills             ▲ ▼        ✕
 4 GATEKEEPER Bella → Ant Nest               ▲ ▼        ✕
 5 FARM       route + fight zone                        ✕
```

Use **+ Add ▾** to add:

| Choice | What it does |
|---|---|
| **Teleport** | how the trip **starts**: a chat command (`.giran`) or an item (Scroll of Escape). Always first. |
| **Gatekeeper** | talk to an NPC and click its buttons (e.g. *Teleport → Ant Nest*). Its **How** can also be *Chat command* or *Use an item* for a teleport in the middle of the trip. |
| **Shop** | walk to a merchant and buy ([section 8](#8-shops)) |
| **Quest** | a quest done at this point of the trip ([section 9](#9-quests)) |
| **Farm spot** | the route to the spot and the **fight zone** (a `.zmap` from Adrenaline's *Settings* folder). Always last. |

- Most zones only need the **teleport** and the **farm spot**. Gatekeepers, shops, buff stops and quests are under **More settings** — its line says what is there (e.g. *gatekeeper Bella · quests: 1*); click **Show** to open them.
- **▲ ▼** move stops and quests; **✕** removes anything (the teleport too).
- The type label on a card (e.g. **GATEKEEPER ▾**) changes a stop's type.
- **Buttons → Pick…**: talk to the NPC in game, then double-click the buttons in the order you click them.
  The editor clicks them in game too, so you see it work.
- **NPC**: type its name or id, or target it in game and press **◎ Set from my target**.

---

## 7. Record routes

Every stop and the farm spot has a **Route** — the walk from the previous place.

1. Stand where the walk starts (for the first stop: **exactly where the teleport lands — wait a second after landing**).
2. Click **● Record**, walk the way in game, click **■ Stop**.
3. Click **Map** to check or fix it on the real game map:
   drag a dot to move it · click to add a point · right-click a dot to delete · **Draw** to sketch · wheel = zoom · drag the map = pan.
   The red dot is your character — **Center on character** jumps to it.

**Fight zone** (farm spot): **Edit** opens the zone's `.zmap` on the game map, **New…** draws a new one. Click to add
corners (a click next to a side adds a corner there), drag to move, right-click to delete. **+ Hole** = an area inside
the fight zone the bot stays out of. **Save fight zone** writes it into Adrenaline's Settings folder (the old file is
kept as `.zmap.bak`) and the farm spot uses it - press **Save** in Gludio Gate.

**Safe zone** (farm spot map only): **🛡 Set safe zone** → click where it should be, and tick its checkbox.
When a buff runs out while farming, the character walks there, kills what followed it, then does the rebuff trip.
Pick a quiet spot near the farm area with no mobs walking through.

**No route needed** — tick it when the NPC stands right where you arrive.

> Map pictures blank? **⚙ Settings → App → Maps folder** and pick Adrenaline's `Maps` folder.

---

## 8. Shops

1. **+ Add → Shop**, set the NPC and its **Route**.
2. **Pick from what <NPC> sells…** — the merchant's full list with grade, type and price. Search, filter, tick items, **Add selected**.
   (Or **+ Add item** and type a name / id.)
3. For each item:
   - **Buy up to** — how many you want to have after shopping.
   - **More ▾**: *when less than* (only buy when you have fewer), *Wear it* (equip after buying), *Go back at* (while farming, go back to buy when you have fewer than this).

Gear is bought once and worn; a shop with nothing to buy is skipped.

**Gear presets** (script **…** menu → *Gear preset (class weapon / armor)…*): pick a class (dwarf, knight, dagger,
archer, fist fighter, polearm, mage, heal, titan, kamael…) and its weapon and armor go into your gear shops — no-grade
at Gludio (Sydnia, Simplon), D and C at Giran: fighters from Graham and Radia, mages (staffs, robes) from **Stanford**
and **Peta**. Edit, copy or add your own presets. A new shop (e.g. Stanford) needs its shop buttons set once with **Pick…**. *Save as a new script* with a preset makes one
script per class.

---

## 9. Quests

A quest is a list of **steps**, done in order:

| Step | What happens |
|---|---|
| **TALK** | travel to an NPC and click its buttons — accept, deliver, turn in |
| **HUNT** | farm at this zone's farm spot until the character has **N × quest item** |

Typical hunting quest: **Talk** (accept) → **Hunt** 20 claws → **Talk** (turn in).

1. **+ Add → Quest**, type its name.
2. **+ Talk step**: NPC, *Get there* (walk / chat command / item), route, **Pick…** the buttons.
   Quest names in NPC windows show as a number like `[17401]` — that's normal, pick it.
3. **+ Hunt step**: pick the quest item from the quest inventory (have at least one first) and the count.
4. Optional: **quest id** (a quest already taken skips its accept step) and **Repeat when finished**.

- Each character keeps **its own progress** — a restart, death or disconnect continues where it stopped.
- The character **stays in the zone until its quest is done**, even after levelling out of it.
- If a turn-in doesn't take the quest items (wrong buttons), the quest is not counted as done — it retries.

---

## 10. Shopping list (gear and supplies)

**🛒 Shopping list** (left side) is **everything the characters buy, for every level** — gear to wear and supplies:

1. **Towns** — one tab per town (e.g. *Gludio*, *Giran*), each with its own **Town teleport** (`.giran`) and shop NPCs. **+ Add town** for another one (up to 9).
2. In a town: **+ Add → Shop** → NPC (e.g. Helvetia), its route from the teleport, **Pick from what … sells**.
3. Each item:
   - **Buy up to** — e.g. 3000 soulshots.
   - **Go back at** — e.g. 300: while farming, below this the character goes to town, buys everything it needs and returns.
   - **Wear it** — gear: equip it after buying.
   - **Only at levels** — a grade (*D grade*) or levels (*Lv 40-45*); empty = every level.
4. **Sell junk** (same page): items sold at every shop visit, before buying.

The character goes to town **only** when an item of its levels runs out or it has no gear for its new levels yet —
otherwise it never walks to a shop.

> Old scripts with shop stops in their zones: **Move the zone shops here…** moves them into the list (by town) and
> keeps the walk to every farm spot the same. Nothing is saved until **Save** — *Undo changes* puts it back.

---

## 11. Check and run

1. Look over each zone once: every stop has a route (or **No route needed** ticked), every shop has items, and the farm spot has a fight zone. A red *not recorded* means a route is missing.
2. In Adrenaline start **`Leveling_1_40.txt`** for the character.
3. Watch the top bar: *Lv 23 – step: Giran shopping* → *farming at Ant Nest*.

What the bot does, over and over:

1. picks the zone(s) for its level
2. does the trip: teleport → stops and quests in your order → farm spot
3. turns the bot on and farms
4. goes back when supplies run low, after a death, when stuck, or when a quest's hunt is done
5. moves to the next zone on level up (scrolls to town first)

Class changes are done **by hand**.

---

## 12. Settings

**⚙ Settings → Bot** (saved in the script's ini; defaults are fine for most):

| Setting | Default |
|---|---|
| Stuck check: no exp for X min → escape and redo the trip | on, 10 min |
| A trip went wrong (e.g. gatekeeper didn't teleport): retry after | 30 s |
| Low supplies: finish the fight first, at most | on, 180 s |
| Between two supply runs wait at least | 10 min |
| Before a teleport, wait for the fight to end up to | 60 s |
| Escape scroll | Scroll of Escape (or Adventurer's, or never) |
| Use the scroll at once, even in a fight (no waiting for the fight to end) | off |
| Don't use the scroll while in a town / town size | on, 3000 |
| Open the editor when the script starts in Adrenaline | off |

**⚙ Settings → App**: theme, language, Adrenaline folder, Maps folder, check for updates at start.

---

## 13. More tools

- **Several scripts** — the **…** next to the script name → *New script* / *Save as a new script*: e.g. `Mage_1_40.txt` + `.ini`. Load the `.txt` you want in Adrenaline for each character. Copies update automatically with new versions.
- **Zone sets** (older scripts only) — shown only when a script still has some. *… → Make this set a separate script* turns one into its own script.
- **Zone packs** — share zones (with routes) as a file: *Zone packs → Export / Import*.
- **Adrenaline settings** (under the script box) — the Adrenaline settings file (from its Settings folder, e.g. *Dagger*) this script loads when it starts, or *each character's own* (the file with its name). Press **Save**; the script loads them in Adrenaline by itself.
- **Game database** — find any item / NPC / skill id.

---

## 14. Tips for a trip that never gets stuck

- ✅ **Start every level range with a teleport.** After a death, restock or stuck check the trip restarts from its first step — a teleport makes that a known spot. Later steps of the same levels don't need one.
- ✅ Prefer a **chat command** (`.giran`) for the trip start: same landing spot every time, free. A Scroll of Escape goes to the *nearest* town, which can change.
- ✅ Record each route **from where the previous step really ends**, and wait a second after a teleport before pressing Record.
- ✅ Check zone levels: *from* the first level *until reaching* the second.
- ✅ After a big change, open each changed route's **Map** once to see that it really goes where you want.

---

## 15. Problems and fixes

| What you see | What to do |
|---|---|
| **Game not connected** | Click the character in **Running now** (it must run `Leveling_1_40.txt` or `Editor.txt`; the exe must be in the same folder as the scripts). |
| **bag not loaded in Adrenaline - relog this character** | The character was in game before Adrenaline started: log it out and in once. |
| L2 shows **Critical Error … system file may have been damaged (Bad name index …)** | A damaged game client file — run your server's updater / full file check. Not caused by Gludio Gate. |
| L2 crashes in **nvd3dum.dll** | NVIDIA graphics driver — update / reinstall it; lower graphics settings when many clients are open. |
| **trip failed (gatekeeper?), trying again** | The gatekeeper didn't teleport: check its **Buttons** (Pick… again), adena, and that the route ends next to it. |
| **quest step failed** | The quest NPC wasn't found: the step's route must end near it; check the NPC name / id. |
| **could not buy … (adena? wrong Dialog?)** | Not enough adena, or the shop's buttons are wrong (**More → Shop buttons → Pick…**). |
| Character walks into walls after a teleport | The route doesn't start where the teleport lands — re-record it from the landing spot. |
| Uses a scroll and comes back again and again | A supply's *Go back when less than* is higher than *Buy up to*, or the shop can't sell it. |
| Route map shows black squares / nothing | **⚙ Settings → App → Maps folder** → Adrenaline's `Maps`. |
| Something else | Send the red lines and the lines starting with *Quest*, *Shop* or *Gatekeeper* from Adrenaline's log in our Discord. |

💬 **Help, news and zone packs: [our Discord](https://discord.gg/PUMUGWgAkY)**
