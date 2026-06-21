# FFAzey

A personal FFXIV overlay + in-game helper suite — DPS meter, raid timeline & callouts, skill-mitigation flashes, headmarker/tether hints, and a one-press dungeon loot pass. One app installs and runs everything.

> **This is the friend-facing README for the public download repo** (`TreviaAI/FFAzey-App`).
> Source for it lives in the private repo at `docs/PUBLIC_REPO_README.md`; copy it to the
> public repo's `README.md` when it changes.

---

## ⚠️ Read this first (Terms of Service)

FFAzey relies on third-party tools (ACT, OverlayPlugin, Dalamud) that interact with the FINAL FANTASY XIV client. **Square Enix's Terms of Service prohibit third-party tools.** Using FFAzey is entirely at your own risk.

**The author (TreviaAI) is NOT responsible for any Square Enix ToS action, account penalties, or bans that may result from using this software. You use it at your own independent risk.**

Keep it private — don't share it publicly, don't show DPS in official/streamed world-race content, and don't advertise it.

---

## Requirements

- **Windows 10/11** (64-bit).
- **FFXIV running in Borderless Windowed mode** (exclusive fullscreen hides all overlays).
- **ACT + OverlayPlugin** — the combat-data source. FFAzey's **Setup** tab can install/point you to these.
- For the in-game plugin features (loot pass, skill flash, timeline bar, headmarkers): **XIVLauncher + Dalamud** (also covered by the Setup tab).
- **WebView2** — the installer adds it automatically if missing.

## Install

1. Download the latest **`FFAzey_x.y.z_x64-setup.exe`** from the [Releases](../../releases/latest) page.
2. Run it. Windows SmartScreen may warn *"Windows protected your PC"* because the app isn't code-signed — click **More info → Run anyway**. (It's an unsigned app shared between friends; that's expected.)
3. Launch **FFAzey** from the Start menu.

## First-time setup

1. Open the **Setup** tab. It shows green/red for each prerequisite (ACT, OverlayPlugin, Npcap, XIVLauncher, Dalamud, the FFAzey plugin).
2. Click the **fix button** next to anything red — it installs or opens the right download. A couple of steps you do yourself (logging into the game once so Dalamud finishes installing).
3. Click **▶ Start FFAzey** — it launches ACT, waits for the data feed, and opens your enabled overlays.
4. In the **Overlays** tab, toggle which overlays you want (DPS meter, timeline, skill flash) and position them.

## Showing the DPS meter & other overlays

FFAzey draws its own overlay windows — **you do NOT add anything to ACT's "OverlayPlugin → add overlay" screen.** To show the DPS meter:

1. **FFXIV in Borderless Windowed** (System Config → Display Settings → Screen Mode). Exclusive Fullscreen hides every overlay.
2. **Data feed green** — Setup tab → the *OverlayPlugin data feed* row must be green (ACT running + its WSServer started). The meter stays invisible until combat data is flowing.
3. **Overlays tab → switch "DPS meter" to On.** A transparent window appears (top-left by default). The Overlays tab also has a **"How do I show the DPS meter?"** button with these same steps.
4. **Hit a striking dummy.** Numbers fill in; out of combat the meter can look empty — that's normal.
5. **Move / resize it:** click **Move / resize**, drag the window by its title bar and pull its edges, then click **Done**. Use the **Scale** slider to size the contents. (*Interactive* is only needed to click into the meter, e.g. a DPS row.)

> Still blank? It's almost always Fullscreen mode (step 1) or the data feed (step 2) — not the overlay itself. The old ACT/OverlayPlugin "add overlay" method still works but isn't needed and is easy to get wrong; the toggles inside FFAzey are the supported way.

## In-game plugin (loot pass, skill flash, timeline bar, headmarkers)

These run inside the game via Dalamud. To install/update the plugin:

1. In-game: `/xlsettings` → **Experimental** → **Custom Plugin Repositories**.
2. Add this URL and enable it:
   ```
   https://github.com/TreviaAI/FFAzey-App/releases/latest/download/repo.json
   ```
3. `/xlplugins` → search **FFAzey** → Install. It auto-updates from then on.

## Updates

- **App:** Setup tab → **Check for updates** (or it checks on launch). It downloads, installs, and relaunches automatically.
- **Plugin:** updates automatically through Dalamud once the repo URL above is added.

## Troubleshooting

- **Overlays don't show over the game** → make sure FFXIV is in **Borderless Windowed**, not exclusive fullscreen.
- **DPS/timeline show no data** → ACT + OverlayPlugin must be running (Setup tab → the *OverlayPlugin data feed* row should be green; if not, start ACT / enable OverlayPlugin's WSServer).
- **Setup says ACT installed but can't launch it** → if you installed ACT from a zip (no installer), start ACT manually once; FFAzey detects it via the data feed.
