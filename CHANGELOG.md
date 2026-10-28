# 🆕 Gludio Gate — what's new

Every change since **3.0.0**, for players. The editor updates itself (click **Yes** when it asks) and updates
all your leveling scripts with it — your zones and settings are never touched.
**After an update, restart your scripts in Adrenaline once.**

---

## 3.0.42 — October 2026

*3.0.26 – 3.0.41 were test builds and never released, so everything below is new in 3.0.42.*

### New
- Quests with a *quest id* find each character's step from the game's quest list. The bot learns it by itself while characters do the quest; then a character whose saved step is wrong is moved to the right one, and one that dropped the quest starts over.
- A quest's *Progress* button opens a window that scrolls through every character: change a character's step (or set it to finished), remove a character so it starts the quest over, or add one, then *Save*.
- *Repeat when finished* sits next to the *Progress* button: on = the character takes the quest again every time, off = once per character.
- Two more themes in *Settings > App*: *Adena gold* (warm black and gold) and *Gludio stone* (warm grey and green). All themes now have a flat, solid look and calmer headings.
- *Copy zone* (next to the zone list's arrows) and *+ Add zone > Paste zone*: a whole zone goes into this or another script. The farm spot and the zone's gatekeeper also have their own *Copy* button, pasted with *+ Add* in another zone.
- *Copy card* on every stop card, and *Paste card* in *+ Add*: a shop (NPC, buttons, route, shortcut, items) can be copied to another zone, the shopping list or another script. Pasted in a town that already has that NPC, its items are added to that card (one walk to the NPC, not two).
- *Shortcut from town* on shop cards: when only that shop has something to buy (e.g. just mana potions), the character walks its shortcut and skips the other shops. With 2 or more shops to visit, the full route is walked. Record it in game or draw it on the map (Auto route can find the way).
- *Auto zone* on the map's fight zone (needs geodata, *Settings > App*): pick a size, click a spot, and the fight area follows the ground the character can walk to, with holes around walls, rocks and cliffs. *Auto holes* does the same inside an area you drew yourself. Undo brings the old zone back.
- *Save as...* on the fight zone map: saves the zone as a new .zmap file, and the farm spot then uses the new one.
- Saving a fight zone warns when Adrenaline would refuse it (two corners closer than 50, or lines that cross) and shows the area or hole with the problem.
- *Delete this town* also works for the first town of the shopping list: the next town takes its place.
- A shopping town that teleports with a *Scroll of Escape* shows a warning: the scroll goes to the nearest town, not to that town's shops. Use the chat command (e.g. *.giran*).

### Fixed
- When a gatekeeper teleport took long to load (many game windows open), the character landed in the farm zone but the bot said *no teleport* and stopped. A late landing now counts as teleported.
- A new character with the name of an old one could skip a quest the old one had finished (*its quests are finished*). Quest progress now remembers which character it belongs to, so the new one does the quest.
- A quest talk step only counts when the NPC's window really opened (3 tries) - before, a character that never got the NPC targeted could save the quest as finished.
- A character started at its farm spot near a zone's landing point thought it was already there, didn't teleport, couldn't find the first NPC and waited for ever. After a failed trip the next try always teleports.
- A character already standing where a zone's teleport lands no longer needs the teleport - it walks on from there.
- A zone that is only quests, all finished by this character, no longer uses its teleport (no more wasted *Scroll of Escape*).
- A zone's *Shortcut route* is always shown on its farm card when it has points, with a delete button.

---

## 3.0.25 — October 2026

### New
- *+ Add > Gift of Vitality (Jack Sage)*: a stop on the trip where the character opens Jack Sage's window and clicks *Receive the Gift of Vitality* (vitality up to level 4 for 2 hours), then goes on. It only goes when the character has no *Blessing of Vitality* (checked by name and by its id 23179), and at most once in 12 hours - so after a death it doesn't walk back to Jack Sage again and again (both can be changed on the card). No NPC id needed - it talks to the Jack Sage in whichever town it is. Record the route to him like for any other stop.
- *+ Add > Talk to an NPC*: the same for any NPC - type its name and the buttons to click.
- *Discord*, *GitHub* and *Support the project* (Revolut) icons in the top bar - click one to open it. *Support the project* is in About too.

### Changed
- Under the zone list, *+ Add zone*, up, down and delete are in one row - *Delete zone* is no longer right under *Add zone*.
- The *Record* buttons are plain until they record; while recording they turn red (*■ Stop*).

### Fixed
- Spanish, Portuguese, Russian and Ukrainian: about 125 texts that were still in English (gear presets, the fight zone map, *Running now*, the top line, What's new...) are translated, and the *How* box shows its whole text.
- After switching dark / light in Settings, the main buttons took the Windows accent color - they stay Gludio green now.
- Recorder: the status text has its own line under the buttons (it ran over the last button).
- Deleting the chat command of a teleport (the trip's first card, a gatekeeper stop set to *Chat command*, or a quest step) no longer turns the card into an empty gatekeeper or removes the teleport card - the card stays while you type the new command.
- The About window fits the screen: a long *What's new* list scrolls, so the buttons at the bottom are always visible.

---

## 3.0.17 — October 2026

- Small fixes.

---

## 3.0.16 — October 2026

*3.0.13 – 3.0.15 were test builds and never released, so everything below is new in 3.0.16.*

### 🗺️ Fight zone editor
- **Edit** / **New…** next to the farm spot's **Fight zone**: draw the fight area on the real game map — click to add corners (a click next to a side adds a corner there), drag to move, right-click to delete.
- **+ Hole**: an area inside the fight zone the bot stays out of.
- **Save fight zone** writes the `.zmap` straight into Adrenaline's `Settings` folder, exactly like Adrenaline's own files. Editing an existing file keeps the old one as `.zmap.bak`.

### ⚙️ Adrenaline settings per script
- Under the script box: **Adrenaline settings** — pick the settings file (from `Adrenaline\Settings`, e.g. *Dagger*) the script loads when it starts, or *each character's own* (the file with its name), or *don't load*.
- Press **Save**: when the script starts in Adrenaline it loads those settings by itself — no more loading them one by one.

### 📜 Scroll out of fights at once
- **Settings → Bot → Use the scroll at once, even in a fight**: when the character has to go to town (supplies low, teleport item, chat teleport, quest done) it reads the Scroll of Escape right away instead of finishing the fight first.

### 🛡️ Fixes
- A teleport item (e.g. Scroll of Escape) waited up to **twice** the "wait for the fight to end" time while mobs were on the character — characters reached town late.
- **Settings → Bot**: a number below its minimum (e.g. a retry wait under 5 s) was silently not saved. The box now turns red and says the minimum.

### 🧹 Removed
- The **Party** window and **Zone stats**.

---

## 3.0.12 — October 2026

### 🧙 Mage gear in the gear presets

- The weapon / armor pickers now also list what **Stanford** (wizard weapons) and **Peta** (wizard armor) sell in Giran — next to Graham and Radia. So D and C **staffs, magic swords, books and robes** can be picked.
- The default **Mage - staff + robe** preset now has **D** gear (Staff of Life, Knowledge robe set) and **C** gear (Sage's Staff, Karmian robe set).
  Already have your presets? **Add the defaults back** adds it, or pick the staff and robe in your own mage preset.
- **Start wizard**: with a mage preset it also adds Stanford and Peta to the Giran shopping list.
- Stanford and Peta are new shops: talk to each once in game and set their shop buttons with **Pick…** (the *Common Items* list).

---

## 3.0.11 — October 2026

*3.0.1 – 3.0.10 were test builds and never released, so everything below is new in 3.0.11.*

### ⚡ Faster and steadier

- **Fast NPCs** — talking to NPCs, clicking their buttons, buying and selling no longer wait fixed pauses: each step goes on as soon as the game answered. A typical shop / gatekeeper / quest visit takes about 1–2 s instead of 5–6 s.
- **Less work for Adrenaline** — the leveling scripts no longer stay connected to Gludio Gate. Before, every character's connection ran all the time; the *Timer Error* / *Access violation* crashes in Adrenaline came with that work.
- **Running now** — the top of the editor shows which characters are leveling right now, live (each script only writes the time every 20 s; nothing is read from the game).
- **Connect on demand** — need the game buttons (Record, Nearby, Set NPC, Pick…)? Click the character in *Running now*. It connects within about 2 s and disconnects by itself 5 minutes after the last game button. `Editor.txt` is no longer needed for that.

### 🛒 Shopping list (was *Supplies*)

- **One shopping list for every level**: gear to wear **and** supplies (soulshots, potions, scrolls) — no more shop stops in every zone.
- **Towns**: a tab per town (e.g. *Gludio*, *Giran*, *Scroll of Escape*), each with its own teleport and its shop NPCs — up to 9 towns. **+ Add town** / **Delete this town**.
- Per item: **Buy up to**, **Go back at**, **Wear it** and **Only at levels** (a grade like *D grade* or a level range like *Lv 40-45*).
- The character goes to town **only** when an item of its levels runs out (less than *Go back at*) or when it has no gear for its new levels yet — then it buys everything it needs and goes back to its farm spot.
- **Move the zone shops here…** — moves the shop stops of all your zones into the list (by town); the walk to each farm spot stays the same. *Undo changes* puts everything back.

### 🧙 Start wizard

- Script **…** menu → **New script with the start wizard…** — pick the levels (e.g. 1 to 40), one zone every N levels, a class **gear preset**, and soulshots / Scrolls of Escape / potions.
- It makes the zones and a **filled shopping list** (the High Five shops of Gludio and Giran with their buttons).
- It never makes up routes: you then record each zone's farm spot and, in the shopping list, the walk from each town's teleport to its shop NPCs — then **Save**.

### 🧭 Simpler zone page

- A zone now shows just its **teleport** and **farm spot**. The gatekeeper, shops, buff stops and quests are behind **More settings** — one line says what is there (e.g. *gatekeeper Bella*, *quests: 1*); **Show** opens them.

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

- Script **…** menu → **Gear preset (class weapon / armor)…** — pick a class (dwarf, knight, dagger, archer, fist fighter, polearm, heal, titan, kamael, …) and its **weapon and armor** go into your gear shops: no-grade at Gludio (Sydnia, Simplon), D and C at Giran (Graham, Radia). Edit, copy or add your own presets.
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
