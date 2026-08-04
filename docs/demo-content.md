# Demo source textures

Shipped **raw PNG** samples for the texLab demo and Fab review. **Default:** use pre-imported assets in plugin **`Content/texLabDemo/`** → Content Browser **`/texLab/texLabDemo/Textures/`**. Reimport from this folder only when plugin Content is missing or you want copies under project Content (`/Game/...`).

Full walkthrough: [../Help/operation-manual.md](../Help/operation-manual.md).

**Inventory (2026-08):** **13 material sets** + **Noise** folder = **71 PNG** files total.

---

## Folder layout

```text
Plugins/texLab/Resources/Demo/
├── README.md
├── Brick/          (5)  T_Brick_BC, T_Brick_Normal, T_Brick_AO, T_Brick_Roughness, T_Brick_Height
├── Carpet/         (5)  full PBR-style set + Height
├── Cliff/          (5)  full PBR-style set + Height
├── Damascus/       (5)  T_Damascus_Diff, Normal, Glossiness, Specular, Height  (legacy channel names)
├── Gold/           (5)  full PBR set incl. Metallic
├── Knit/           (5)  full PBR-style set + Height
├── Magma/          (6)  full PBR set incl. Metallic + Height
├── Marble/         (5)  full PBR-style set + Height
├── Plaster/        (5)  full PBR-style set + Height
├── Sand/           (5)  full PBR-style set + Height
├── Scarf/          (7)  full PBR set incl. Metallic, Specular, Height
├── Wood/           (5)  full PBR-style set + Height
└── Noise/          (8)  T_Blue_Noise, T_Bnw_Noise, T_Cloud_Noise, T_Combo_Noise, T_Combo2_Noise,
                         T_Fractal_Noise, T_Perlin_Noise, T_Voronoi_Noise
```

Shipped **`.uasset`** counterparts live under:

```text
Plugins/texLab/Content/texLabDemo/Textures/<Folder>/
```

Content Browser path: **`/texLab/texLabDemo/Textures/<Folder>/`**.

### File list (exact names)

| Folder | PNG files |
|--------|-------------|
| **Brick** | `T_Brick_AO`, `T_Brick_BC`, `T_Brick_Height`, `T_Brick_Normal`, `T_Brick_Roughness` |
| **Carpet** | `T_Carpet_AO`, `T_Carpet_BC`, `T_Carpet_Height`, `T_Carpet_Normal`, `T_Carpet_Roughness` |
| **Cliff** | `T_Cliff_AO`, `T_Cliff_BC`, `T_Cliff_Height`, `T_Cliff_Normal`, `T_Cliff_Roughness` |
| **Damascus** | `T_Damascus_Diff`, `T_Damascus_Glossiness`, `T_Damascus_Height`, `T_Damascus_Normal`, `T_Damascus_Specular` |
| **Gold** | `T_Gold_AO`, `T_Gold_BC`, `T_Gold_Metallic`, `T_Gold_Normal`, `T_Gold_Roughness` |
| **Knit** | `T_Knit_AO`, `T_Knit_BC`, `T_Knit_Height`, `T_Knit_Normal`, `T_Knit_Roughness` |
| **Magma** | `T_Magma_AO`, `T_Magma_BC`, `T_Magma_Height`, `T_Magma_Metallic`, `T_Magma_Normal`, `T_Magma_Roughness` |
| **Marble** | `T_Marble_AO`, `T_Marble_BC`, `T_Marble_Height`, `T_Marble_Normal`, `T_Marble_Roughness` |
| **Plaster** | `T_Plaster_AO`, `T_Plaster_BC`, `T_Plaster_Height`, `T_Plaster_Normal`, `T_Plaster_Roughness` |
| **Sand** | `T_Sand_AO`, `T_Sand_BC`, `T_Sand_Height`, `T_Sand_Normal`, `T_Sand_Roughness` |
| **Scarf** | `T_Scarf_AO`, `T_Scarf_BC`, `T_Scarf_Height`, `T_Scarf_Metallic`, `T_Scarf_Normal`, `T_Scarf_Roughness`, `T_Scarf_Specular` |
| **Wood** | `T_Wood_AO`, `T_Wood_BC`, `T_Wood_Height`, `T_Wood_Normal`, `T_Wood_Roughness` |
| **Noise** | `T_Blue_Noise`, `T_Bnw_Noise`, `T_Cloud_Noise`, `T_Combo_Noise`, `T_Combo2_Noise`, `T_Fractal_Noise`, `T_Perlin_Noise`, `T_Voronoi_Noise` |

---

## Naming rules

- Keep the **`T_` prefix** and **suffix** exactly as listed — texLab reads meaning from the file name.
- **`T_Damascus_Diff`** maps to Base Color via the `_Diff` / `_diff` semantic alias (case-insensitive).
- **Noise** textures use `_Noise` suffix; Batch groups them as **one texture per group** (material base = name before `_Noise`, e.g. `Blue`, `Perlin`).
- Use **PNG** (8-bit or 16-bit). Other formats work if Unreal imports them; PNG is the default for this demo.
- **Base Color / Diff** → sRGB; **Normal / AO / Roughness / Metallic / Height / Noise** → linear (adjust import settings after import if needed).

Optional later: add a pre-packed `T_Magma_ORM.png` (or similar) under a material folder for **Unpack** demos.

---

## Optional reimport into Unreal

Use only when **`/texLab/texLabDemo/`** is not present or you need project-local Content:

1. Open your project with **texLab** enabled.
2. In Content Browser create **`/Game/texLabDemo/Textures/`** (or your preferred folder).
3. Create a subfolder per material set (`Brick`, **Gold**, `Magma`, `Noise`, …) if it does not exist.
4. **Import** PNGs from `Plugins/texLab/Resources/Demo/<Folder>/` into that folder.
5. Prefer **import from disk** (keep source file path) — required for the provenance check in Fab review.

Example paths after reimport: `/Game/texLabDemo/Textures/Gold/T_Gold_BC`, `/Game/texLabDemo/Textures/Magma/T_Magma_BC`.

The PNGs in **`Resources/Demo/`** remain the tracked source of truth for names and Fab packaging.

---

## Shipped demo (plugin Content)

| Item | Content Browser path |
|------|----------------------|
| Demo textures | **`/texLab/texLabDemo/Textures/<Folder>/`** |
| Preview map | **`/texLab/texLabDemo/Maps/texLab_Demo_Map`** |

Open the preview map to assign Material Instances created with texLab (cube / sphere / plane meshes). See the Operation Manual demo section.

---

## Suggested exercises

| Folder | Good for |
|--------|----------|
| **Magma**, **Gold**, **Scarf** | Full **Safe** pack (BC + AO + Roughness + Metallic + Normal) |
| **Damascus** | **Glossiness**, **Specular**, **Diff** (legacy naming) |
| **Brick**, **Sand**, **Wood**, … | Standard sets with **Height** (env-style strategies) |
| **Noise** | Single-map **Noise** semantic; Batch = one texture per group |

**Batch scope:** add **`/texLab/texLabDemo`** (or `/texLab/texLabDemo/Textures`) → Scan → Rebuild Groups → expect **13 material groups** (Brick … Wood) plus **8 single-texture Noise groups**.
