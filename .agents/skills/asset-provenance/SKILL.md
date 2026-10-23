---
name: asset-provenance
description: Create, import, or specify game art and audio assets with recorded provenance, license status, dimensions, and import settings in the studio asset register, and verify them in the engine where possible. Use when adding sprites, textures, animations, UI art, shaders, effects, or sounds, generating assets with a tool, or auditing asset rights.
metadata:
  pack: codex-game-studio
  version: "1.0"
---

# Asset provenance

Every asset in the game has a known origin and rights status, and nothing is described as made or checked when it was not.

## Register

The project register is `studio/assets/REGISTER.md`. If missing, copy [assets/REGISTER.md](assets/REGISTER.md) there. Edit it only when you are its assigned owner; otherwise put proposed rows in your report for the lead.

## Steps

1. Read approved visual references and existing assets. Note constraints: silhouette, palette, camera and scale, contrast, animation, UI readability on the target device.
2. Check which tools this session actually has (image generation, editing, audio, animation). If none, deliver concrete specifications or clearly labeled placeholders.
3. Produce or import the asset. Keep source files and deterministic export settings where practical.
4. For raster output, verify dimensions, transparency, frame alignment, and import settings with an available tool.
5. Check the asset in the engine when possible: contrast, effect clutter, UI scaling, animation transitions, shader compatibility.
6. Add one register row per asset: path, purpose, source/creator/tool, license or rights status, dimensions/format, import settings, validation done.

## Rules

- Unknown rights stay `unknown`; never label them cleared.
- Mark placeholders as placeholders.
- Do not buy assets or copy proprietary ones without the user's authorization.
- Never imply an asset was generated, animated, imported, or visually inspected when it was not.
- Report texture, draw-call, or frame-time costs only with their test context; visual inspection says nothing about device performance.
