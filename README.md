# Drakengard (PS2) — Widescreen + Camera patch

A patch for **Drakengard (PAL, SLES-52322)** that:

- reworks the ground-battle camera to something closer to **NieR: Automata** (as far as the game allows);
- makes the game **16:9 widescreen** (based on ElHecht's Widescreen 16:9 patch, included);
- fixes the **UI and HUD** that the widescreen patch leaves stretched — menus, HUD, pause screens, dialogue,
  mission results, aerial battle HUD, world map and more now keep their correct 4:3 proportions;
- shows **CG movies in 4:3** with black bars instead of stretched.

Made by **Lithium Elf** with Codex and Claude.

📺 Video: **https://www.youtube.com/watch?v=jQjbufm0hEc&feature=youtu.be**

> This repository contains **no game files**. You need your own copy of the game.

---

## Requirements

**PAL version only** — Drakengard (Europe) (En,Fr,De,Es,It), **SLES-52322**. The US and Japanese versions will not work.

Check your ISO before patching:

| | |
|---|---|
| PCSX2 game CRC | `79585776` |
| ISO size | `4,445,044,736` bytes |
| ISO SHA-1 | `64a219042ca2f82327a5e3e35f0a69591d6bf631` |

If your SHA-1 is different, the ISO patch may not apply correctly — use option **B** (PCSX2 patch), which only needs
the CRC `79585776`.

---

## Download

Get the latest archive from **[Releases](../../releases)**. It contains:

| File | Use |
|---|---|
| `Drakengard_PAL_Widescreen_Camera_ISO.ips` | patch for the whole ISO (PCSX2, PS3, PS2) |
| `Drakengard_PAL_Widescreen_Camera_SLES_523.22.ips` | the same patch for the game executable only, if you rebuild the ISO yourself |
| `PCSX2_patch/79585776.pnach` | the same patch as a PCSX2 *Patches* entry, for the original ISO |

The same files are in the [`patches`](patches) folder of this repository.

---

## Installation

### A) Patch the ISO — PCSX2, PS3 with PS2 hardware backward compatibility, PS2

1. Make a **copy** of your Drakengard PAL ISO. Never patch your only copy.
2. Download **Lunar IPS**.
   > ⚠️ **Do not use Floating IPS.** The ISO is larger than 4 GB, and Floating IPS produces a truncated
   > (smaller, broken) file with it.
3. Apply `Drakengard_PAL_Widescreen_Camera_ISO.ips` to the copy.
4. Check the result: the patched ISO must have **exactly the same size** as the original —
   `4,445,044,736` bytes. Optionally:

   | | |
   |---|---|
   | patched ISO SHA-1 | `b0f9c27b88dbd6e20f5190487e51ab16c290a62b` |
   | PCSX2 game CRC | `C5CFB3F1` |

5. Play:
   - **PCSX2:** boot the patched ISO and set Aspect Ratio to **16:9**. Don't enable any widescreen patch or cheat for
     it — everything is already inside the game.
   - **PS3 with hardware PS2 backward compatibility, or a PS2:** run the patched ISO the way you normally run your PS2
     games/backups, with a 16:9 output.

### B) PCSX2 only, without patching the ISO

1. Copy `PCSX2_patch/79585776.pnach` into PCSX2's `patches` folder
   (portable build: `<PCSX2 folder>\patches\`; installed: `Documents\PCSX2\patches\`).
   If a file with this name already exists there, rename or move it first.
2. Right-click Drakengard → **Properties → Patches** → enable **Drakengard Widescreen + Camera v1**.
3. **Disable** PCSX2's built-in *Widescreen 16:9* patch for this game and any widescreen cheats
   (this patch already contains it).
4. Set Aspect Ratio to **16:9** and start the game from a fresh boot (not from an old save state).

### PCSX2 notes

- CG movies in 4:3 need **Settings → Graphics → Screen Offsets: ON**. With it off PCSX2 ignores this part and the movies
  stay stretched.
- Don't load save states made without the patch.

---

## Tested on

- **PCSX2** (Fast Boot on and off)
- **Japanese PS3 with hardware PS2 backward compatibility** (real PS2 hardware)

Not tested on a real PS2, but it should work there too. Tested areas: ground battles, aerial battles, boss fights,
menus and the interface in general.

---

## Known issues / not done yet

- Advanced settings screen is still stretched (its background is a single picture).
- The world map picture itself is still stretched (the mission list, prompt and cursor are fixed).
- The 3D sword on the Weapon Status page, "exp" popups above enemies and some parts of the dragon HUD are not fixed yet.

Found something else? Please open an **[issue](../../issues)** with a screenshot and where it happens.

---

## Uninstall

- Patched ISO: go back to your original copy.
- PCSX2 patch: disable it in *Properties → Patches* or delete the `.pnach`.

---

## Credits

- **Lithium Elf** — camera, UI and HUD fixes (made with Codex and Claude)
- **ElHecht** — original Widescreen 16:9 patch
