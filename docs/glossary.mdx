# Glossary

Domain terms used in the texLab UI and documentation.

## Packed texture acronyms


| Term     | Typical channels                                     | Notes                                                    |
| -------- | ---------------------------------------------------- | -------------------------------------------------------- |
| **ORM**  | Occlusion (R), Roughness (G), Metallic (B)           | UE-friendly packed PBR set                               |
| **RMA**  | Roughness (R), Metallic (G), Ambient Occlusion (B)   | Studio variant; must be explicit in semantic DB          |
| **ARM**  | Ambient Occlusion (R), Roughness (G), Metallic (B)   | Another common ordering — never infer from letters alone |
| **MSR**  | Metallic (R), Specular/Smoothness (G), Roughness (B) | Legacy/spec-gloss workflows                              |
| **AORH** | AO (R), Roughness (G), Height (B)                    | Env Height pack; aliases `_ARH` / `_ORH` (same map)      |
| **ORMH** | AO (R), Roughness (G), Metallic (B), Height (A)      | Env ORM + Height                                         |
| **RGH**  | Roughness (R), Glossiness (G), Height (B)            | Env gloss-oriented Height pack                           |


texLab maps these via **explicit JSON rules**, not filename letter heuristics. Output presets: `ue_env_*_normal`.

## Pipeline


| Term                   | Meaning                                                                                                                                                                       |
| ---------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Semantic rule**      | JSON entry mapping tokens / names to channel roles and confidence                                                                                                             |
| **Preset**             | Output recipe: compression (TC_Masks, TC_Normalmap), sRGB flags, channel graph                                                                                                |
| **Output recipe**      | Concrete pack definition applied to a material group or manual session                                                                                                        |
| **Channel slot**       | One output channel (R/G/B/A) with extract/remap/adjust stack                                                                                                                  |
| **Adjustment stack**   | Ordered invert / remap / contrast / gloss→rough ops on a channel                                                                                                              |
| **Gloss→Rough**        | Linear conversion to UE roughness: Invert `1-G` (default) or InvertSquare `(1-G)^2`                                                                                           |
| **Gray / luminance**   | Source sample for singles: R-only / equal-RGB → R; else Rec.709 luma                                                                                                          |
| **Assembly**           | Build packed outputs from **loose single** textures (BaseColor, Rough, Metal, AO, Height, Normal XY, …)                                                                       |
| **Repack**             | Extract / reorder channels from **already packed** RGBA / BC5 / BC7 maps                                                                                                      |
| **Unified pack graph** | One resolve→`TexLabPackExecutor`→write path for Assembly and Repack                                                                                                           |
| **requiredInputs**     | Recipe-declared semantics that must be present before Create Outputs / batch execute                                                                                          |
| **Material template**  | JSON descriptor: output TextureKind (+ optional semantic) to MI parameter names                                                                                               |
| **MaterialBase**       | Batch grouping key from filenames: strip map suffixes/tokens (`_ORM`, `_Roughness`, `_rg`, `_R`, `_mt`, `_M`, `-ao`, …), optional numeric peel; Core `FTexLabMaterialBaseOps` |
| **Single-map alias**   | Explicit TokenAlias in semantic DB for loose maps (`_Roughness`, `_rg`, `_R`, …). Last-token match for 1-letter aliases; no letter-order guessing                             |
| **Dry-run**            | Batch plan with zero asset writes                                                                                                                                             |




## Source fidelity


| Term                            | Meaning                                                                                          |
| ------------------------------- | ------------------------------------------------------------------------------------------------ |
| **Source art**                  | Highest-fidelity texture data (ImportData file path or embedded `FTextureSource`)                |
| **Source reason**               | Enum explaining which resolver step produced an input                                            |
| **Quality tier**                | Honesty label: External / EmbeddedSource / DerivedFallback                                       |
| **Platform / derived fallback** | Opt-in read of uncompressed platform mip when source art missing; BC refused; default fail       |
| **Provenance**                  | `AssetUserData` on outputs: sources, preset id, schema version, job id, quality tier, timestamps |




## Settings and policies


| Term                  | Meaning                                                                                                    |
| --------------------- | ---------------------------------------------------------------------------------------------------------- |
| **Resolution policy** | How to align mismatched input sizes before packing: Fail / Largest area / Smallest area / First / Explicit |
| **Output root**       | Default content path for generated textures (`/Game/texLab/Output`)                                        |
| **Preview size**      | Max edge length for live preview downsample (256 / 512 / 1024)                                             |
| **Overwrite policy**  | Skip / Create New / Replace when target asset exists                                                       |
| **Concurrency cap**   | Max parallel CPU worker tasks for jobs                                                                     |


