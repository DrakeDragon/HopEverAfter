# 🐇 Hop Ever After

**A one-tap fairytale hopping game with 100 realms, 800 trails, 200 boss fights, 12 playable heroes and a 100-chapter novel.**

Tap to hop. Tap again in the air to double hop. Hold for higher. That is the entire control scheme, from the first realm to the last.

> Play it: `https://<your-username>.github.io/<repo-name>/`

---

## The idea

The Great Book of Tales has one hundred pages, and every page is a whole world. Someone is stamping **THE END** across them, freezing every tale mid-sentence. Wren, a girl who lives in the margins and belongs to no story, is the only one who can hop from page to page. Collect crumbs, gather friends from every tale, free each realm's frozen villain, and find out who drew you in the margin.

## How to play

| Action | Control |
|---|---|
| Hop | Tap (or Space / Up / W) |
| Double hop | Tap again in mid-air |
| Hop higher | Hold the tap |
| Short hop | Release early |

- You run automatically. Everything is about timing your hops.
- Grab the realm's crumb pickups. Every **6 crumbs** adds a friend who follows your party.
- **Matching friends merge on their own** into stronger ones (6 tiers per realm), which grants hearts, a wider crumb magnet, and more damage in boss fights.
- Falling in a pit or touching an obstacle costs a heart. Lose them all and you retry the trail; your party is restored from the start of that trail.
- Boss fights: your party does the fighting automatically. You only dodge. Hop the ground shots, **stay low** under the high bars, and hop the wide waves.

## What's in the game

### Scale
- **100 realms** in **10 Books** (fairy tales, folklore, myth, Norse and Arthurian legend, cosmic fantasy).
- **6 to 10 trails per realm**, 800 trails in total, longer in later realms.
- **A mini-boss** halfway through every realm and a **boss** at the end: 200 fights.
- **600 friends to discover** (6 per realm), shown in the in-game Storybook.
- A realm unlocks when you clear the one before it.

### Obstacles and gadgets
- Spikes, rolling wheels, bouncing balls, swinging spiked pendulums and flyers.
- Springboards, updraft wind zones, crumbling platforms, sliding platforms and vanishing ghost stones.
- Obstacles use a contrasting color, a white outline and a danger glow so they never blend into the stage. The palette flips automatically between dark and light backgrounds.
- Every level is generated from a seeded, physics-checked generator, so every jump in every trail is possible.

### Power-ups
Every friend merge triggers a power-up, and ✨ capsules float on the trails too:
- 🛡️ **Shield**: blocks one hit.
- 🧲 **Magnet surge**: pulls in crumbs.
- ⭐ **Star dash**: invincible, and smashes flyers, wheels and balls.
- ❤️ **Heart**: restores a heart.
- ✖2 **Double crumbs**: for a short time.

### Secret shortcuts
On some trails a hidden golden 🔑 ring floats high above a platform. Double hop through it to warp ahead, skip a chunk of the trail, and earn a free friend and bonus stars. Each realm tracks its secrets on the world map.

### Heroes
Earn ⭐ stars from trails, bosses and secrets, then spend them in **🧙 Heroes** to level characters up to 10. Heroes unlock as you clear realms:

| Hero | Unlock (realms cleared) | Perk |
|---|---|---|
| Wren | 0 | Longer safety after a hit |
| Crumb | 1 | Stronger crumb magnet |
| Quill | 4 | Very forgiving late jumps |
| Pip | 8 | Power-ups last longer |
| Hazel | 12 | Chance of bonus crumbs |
| Sir Rook | 18 | Starts each trail with a shield |
| Mabel | 25 | Bigger boss damage |
| Prince Finn | 35 | Extra hearts as he levels |
| Ember | 50 | Merges may spark a bonus power-up |
| Luna | 65 | Magnet range and jump grace |
| Rex | 80 | Mighty boss damage |
| Aurora | 95 | A little of everything |

### The novel: *The Hundred Pages*
About 13,600 words in 100 short chapters plus a prologue and epilogue, tied to the realms and bosses. Each chapter has two short pages: the first when you enter a realm, the second after you beat its boss. Re-read unlocked chapters from **📖 Storybook → 📜 Read the Novel**.

### Look and sound
Cyan and magenta UI theme, procedurally drawn creatures for every realm, unique palettes, scenery, weather particles (snow, embers, petals, fireflies, bubbles and more) and synthesized sound effects. There are no image or audio files to load.

---

## Deploying to GitHub Pages

1. Create a new GitHub repository.
2. Upload everything in this folder to the repository root (keep the folder structure).
3. In the repo go to **Settings → Pages**.
4. Under **Build and deployment**, choose either:
   - **Deploy from a branch**: select `main` and `/ (root)`, or
   - **GitHub Actions**: a ready-made workflow is included at `.github/workflows/pages.yml`.
5. Wait a minute, then open `https://<username>.github.io/<repo>/`.

Open it on your phone and use **Add to Home Screen** for a full-screen, offline-capable install (the included service worker caches the game after the first visit).

### Files

```
index.html            the entire game (HTML, CSS, JS in one file)
manifest.webmanifest  home-screen install info
sw.js                 offline cache
icons/                192px and 512px app icons
404.html              friendly not-found page
.nojekyll             tells GitHub Pages to serve files as-is
.github/workflows/    optional Pages deploy workflow
```

No build step, no dependencies, no external requests.

## Saving

Progress (cleared realms, discovered friends, stars, hero levels, secrets found, sound setting) is stored in your browser's `localStorage` under `hopeverafter_v2`. Clearing site data resets it.

## Customizing

Everything lives in `index.html`:
- `GEN_ROWS`: one line per realm 24 to 99 (name, emoji, biome, hue, six friend names, boss, boss type, taunt, blurb).
- `BIOMES`: the visual templates (sky, hills, platforms, hazards, weather).
- `NOVEL`: every chapter of the story.
- `HEROES`: character looks, perks and unlock thresholds.
- `trailsOf`, `stretchCfg`, `bossHpFull`: trail counts, difficulty and boss health.

## Testing notes

During development the level generator was checked so that every platform-to-platform jump is physically possible (0 impossible jumps across all 800 trails), a test bot cleared a sample of 160 trails across the whole game with no falls, and mini-bosses and bosses were verified winnable in every realm tested. The game has been rendered and screenshot-tested at phone size in a headless browser, but **not yet play-tested on real phones**, so expect to tune difficulty. Bots do not dodge hazards, so obstacle fairness is by design rather than measured.

## Credits

Game design, code, art and story generated with Claude for Tim. Fairy tales and folklore referenced are from the public domain or traditional folk sources; all characters and text in the novel are original retellings.

## License

No license is included. Add one (for example MIT) before inviting contributions or reuse.
