---
title: E3CNC MGN12H leadscrew variant - parts inventory
doc-type: inventory
authored-by: Claude (Opus 5), directed by Dan (dig-flowspace)
compiler: dan
llm-assisted: true
llm-model: claude-opus-5 (Opus 5, 1M context)
llm-role: Parsed the STEP assembly graph (NEXT_ASSEMBLY_USAGE_OCCURRENCE edges) via a generated Python script, then wrote all prose and tables in this file.
llm-scope-limit: Names, nesting and placement counts only. No geometry was read, so no dimension here is measured.
human-review: pending - nothing in this file has been checked against the CAD
source: Ender3CNC/Developer_MODS/E3CNC_MGN_BETA/E3CNC_MGN_BETA.step
source-format: ISO 10303-21 STEP, schema AP214
source-exported: 2026-02-27
source-branch: E3CNC_MGN12H_LEADS
date-created: 2026-09-07
date-modified: 2026-09-07
---

# E3CNC MGN12H - leadscrew variant: full parts inventory

> **Scope.** Every component in the `E3CNC_MGN12H_LEADS` branch of the BETA
> MGN CAD, with its parent/child nesting exactly as the author built it.
> The belted variant that shares the same file is *not* covered here.

## Provenance

| | |
|---|---|
| **Source file** | `Ender3CNC/Developer_MODS/E3CNC_MGN_BETA/E3CNC_MGN_BETA.step` |
| **Format** | ISO 10303-21 STEP, schema AP214 (`AUTOMOTIVE_DESIGN`) |
| **Units** | millimetre / radian |
| **Exported** | 2026-02-27, Autodesk Translation Framework v14.24 via ST-Developer v20.1 |
| **Top-level document** | `E3CNC_MGN v19` |
| **This branch** | `E3CNC_MGN12H_LEADS` (STEP entity `#711590`) |
| **Occurrences in branch** | 255 |
| **Extracted** | by parsing `NEXT_ASSEMBLY_USAGE_OCCURRENCE` parent/child edges |

The author's own warning, from the mod's `readme.md`, stands over all of this:

> *"These are VERY VERY BETA CAD's, they have yet to been tested."*

## How to read the names

Fusion 360 writes **two** names for every component, and they often disagree.

- **The label** - what the author typed in the browser tree. This is the
  intent, and it carries his shopping tags:
  - `[BUY]` - source it yourself.
  - `[ENDER3]` - salvage it from the donor printer.
- **The product name** - the internal geometry/library name Fusion reused,
  frequently a leftover from whatever part was copied to make this one.

This document leads with **the label**. Where the product name differs it is
shown after `<- modelled as`. When the two disagree about a *specification* -
not just a name - that is recorded under
[Where the source names disagree](#where-the-source-names-disagree).

In the tree: `+` is a sub-assembly, `-` is a leaf, and `xN` means that
component appears N times **in that parent**.

## Where this branch sits

The file holds one root document with both variants under it:

```
E3CNC_MGN v19                        <- the exported document
+-- E3CNC_MGN12H_BELTED              <- belted variant (not covered here)
+-- E3CNC_MGN12H_LEADS               <- THIS DOCUMENT
```

Worth knowing: the two variants are **organised differently**. The belted
version hangs the gantry, Z axis and spindle mount off its own root. The
leadscrew version buries almost everything inside
`Ender3 pro Frame > mgn mod`, so the frame node is where the real machine
lives - not a bare list of extrusions.

## Assembly tree

```text
+ E3CNC_MGN12H_LEADS   <- modelled as `Ender3-V2 Print model_1`
  + Corner_ brackets
    - 608zz bearing
    + Back_bracket_L
      + D2F-L Microswitch v1
        - Contacts
        - Lever
        - Plunger
        - Switch Body
      - M3 Threaded Insert  x2   <- modelled as `(Unsaved)`
      - M3x10 BHCS [BUY]  x2   <- modelled as `M3x10 SHCS`
      - Y_belt_clamp
    + Back_bracket_L (Mirror)
      + D2F-L Microswitch v1
        - Contacts
        - Lever
        - Plunger
        - Switch Body
      - M3 Threaded Insert  x2   <- modelled as `(Unsaved)`
      - M3x10 BHCS [BUY]  x2   <- modelled as `M3x10 SHCS`
      - Y_belt_clamp
    + bracket_FL_sexy_bearing_optional
      - 608zz bearing
      - bracket
      - bracket (Mirror)
      + x_belt_clamp
        - M3 Threaded Insert  x2   <- modelled as `(Unsaved)`
        - M3x10 BHCS [BUY]  x2   <- modelled as `M3x10 SHCS`
    - M5x16 BHSC [BUY]  x20   <- modelled as `M5X8Pan Head Screw`
    - M5x40 BHSC [ENDER3]  x4   <- modelled as `M5X8Pan Head Screw`
  + Ender3 pro Frame
    - 4020 400mm  x2
    - 4040 290mm  x2
    - 4040 300mm - Cut to size
    + M5x8 BHCS + tnut [ENDER3]  x4   <- modelled as `M5x10 BHCS`
      - M5 Shim Washer [BUY]   <- modelled as `M5 Shim Washer`
    + mgn mod
      + 10x11 Chain X v1   <- modelled as `10x11 Chain X`
        - 10x11 Chain Link v1  x18
        - 10x11 Fixed End v1
        - 10x11 Unfixed End v1
        - x chain mount
      + 10x11 Chain Y   <- modelled as `10x11 Chain X`
        - 10x11 Chain Link v1  x22
        - 10x11 Fixed End v1
        - 10x11 Unfixed End v1
        - y chain mount
        - y chain mount back
      - 608zz bearing
      + xy joints_3x Xaxis rods
        + 42-34 motor_Standard  x3
          - Z coupler_Standard
          - Z threaded rod_Standard
        + D2F-L Microswitch v1
          - Contacts
          - Lever
          - Plunger
          - Switch Body
        - M3x10 BHCS v1  x3   <- modelled as `M3x10 BHCS`
        + xy_2hole
          - Component3037
          - Two-trees Anti-Backlash TR8x8 v1   <- modelled as `Anti-Backlash_Nut_TR8x4`
        + xy_2hole (Mirror)
          - Component3165
          - Two-trees Anti-Backlash TR8x8 v1   <- modelled as `Anti-Backlash_Nut_TR8x4`
      + Z_axis_150mm
        - 2020 150mm - Cut to size
        - 2020 150mm Cut to size
        - Component3091
        + D2F-L Microswitch v1
          - Contacts
          - Lever
          - Plunger
          - Switch Body
        - leadscrew [ENDER3]
        - M3 Threaded Insert  x2   <- modelled as `(Unsaved)`
        - M3x10 BHCS [BUY]  x2   <- modelled as `M3x10 BHCS`
        - M3x10 BHCS v1  x18   <- modelled as `M3x10 BHCS`
        - M3x40 [ENDER3]  x4   <- modelled as `M3X40-P_Standard`
        - M3x8 SHCS [BUY]  x12   <- modelled as `M3x8 SHCS`
        - M5x16 BHSC [BUY]  x10   <- modelled as `M5X8Pan Head Screw`
        + MGN12 150mm  x2
          - MGN12H Carriage
        - MGN12C Slide Block v1  x2   <- modelled as `MGN12C Slide Block`
        - Nema 17 42-34 Z motor [ENDER3]   <- modelled as `42-34 motor_Y-Axis`
        - Two-trees Anti-Backlash TR8x8 v1   <- modelled as `Anti-Backlash_Nut_TR8x4`
        - xz_gantry_plate 3x rods
        - Z coupler [ENDER3]   <- modelled as `Z coupler_Standard`
        + z_bottom 608Z
          - 608zz bearing
        + Z_motor_spacer_new v1  x2
          - Component3086
        + z_top 608Z
          - 608zz bearing
        + Ø65mm router clamp V1   <- modelled as `Supporto mandrino`
          + Component3087
            - Component3088
          - M3 Threaded Insert  x2   <- modelled as `(Unsaved)`
          - M5 hexnut [BUY]  x4   <- modelled as `M5 Hexnut`
          - M5x30  x4   <- modelled as `M5X30 Pan Head Screw_Standard`
          + z nut_Standard
            - M3x16 BHCS [ENDER3]  x2
    + mgn12h 300 X
      - MGN12 Rail - 300mm
      - MGN12H Carriage  x2
    + mgn12h 300 X (Mirror)
      - MGN12 Rail - 300mm
      - MGN12H Carriage  x2
    + mgn12h 360 Y
      - MGN12 Rail - 300mm
      - MGN12H Carriage  x2
    + mgn12h 360 Y (Mirror)
      - MGN12 Rail - 300mm
      - MGN12H Carriage  x2
  - Spoilboard
```

## Parts tally

Counts are **occurrences within this branch** - every placement, including
mirrored copies. Sub-assembly rows are marked `assembly`; their contents are
listed separately in their own rows, so **do not add assembly rows to part
rows** when totalling.

### Linear motion (MGN12)

| Qty | Component | Kind |
|----:|-----------|------|
| 10 | MGN12H Carriage | part |
| 4 | MGN12 Rail - 300mm | part |
| 2 | MGN12 150mm | assembly |
| 2 | MGN12C Slide Block v1 | part |
| 1 | mgn12h 300 X | assembly |
| 1 | mgn12h 300 X (Mirror) | assembly |
| 1 | mgn12h 360 Y | assembly |
| 1 | mgn12h 360 Y (Mirror) | assembly |

### Aluminium extrusion

| Qty | Component | Kind |
|----:|-----------|------|
| 2 | 4020 400mm | part |
| 2 | 4040 290mm | part |
| 1 | 2020 150mm - Cut to size | part |
| 1 | 2020 150mm Cut to size | part |
| 1 | 4040 300mm - Cut to size | part |

### Leadscrew drive

| Qty | Component | Kind |
|----:|-----------|------|
| 3 | Two-trees Anti-Backlash TR8x8 v1 | part |
| 3 | Z coupler_Standard | part |
| 3 | Z threaded rod_Standard | part |
| 1 | leadscrew [ENDER3] | part |
| 1 | Z coupler [ENDER3] | part |
| 1 | z nut_Standard | assembly |

### Motors

| Qty | Component | Kind |
|----:|-----------|------|
| 3 | 42-34 motor_Standard | assembly |
| 1 | Nema 17 42-34 Z motor [ENDER3] | part |

### Bearings

| Qty | Component | Kind |
|----:|-----------|------|
| 5 | 608zz bearing | part |
| 1 | bracket_FL_sexy_bearing_optional | assembly |
| 1 | z_bottom 608Z | assembly |
| 1 | z_top 608Z | assembly |

### Endstops

| Qty | Component | Kind |
|----:|-----------|------|
| 4 | Contacts | part |
| 4 | D2F-L Microswitch v1 | assembly |
| 4 | Lever | part |
| 4 | Plunger | part |
| 4 | Switch Body | part |

### Drag chain

| Qty | Component | Kind |
|----:|-----------|------|
| 40 | 10x11 Chain Link v1 | part |
| 2 | 10x11 Fixed End v1 | part |
| 2 | 10x11 Unfixed End v1 | part |
| 1 | 10x11 Chain X v1 | assembly |
| 1 | 10x11 Chain Y | assembly |

### Spindle / router mount

| Qty | Component | Kind |
|----:|-----------|------|
| 1 | Ø65mm router clamp V1 | assembly |

### Fasteners & inserts

| Qty | Component | Kind |
|----:|-----------|------|
| 30 | M5x16 BHSC [BUY] | part |
| 21 | M3x10 BHCS v1 | part |
| 12 | M3x8 SHCS [BUY] | part |
| 10 | M3 Threaded Insert | part |
| 8 | M3x10 BHCS [BUY] | part |
| 4 | M3x40 [ENDER3] | part |
| 4 | M5 hexnut [BUY] | part |
| 4 | M5 Shim Washer [BUY] | part |
| 4 | M5x30 | part |
| 4 | M5x40 BHSC [ENDER3] | part |
| 4 | M5x8 BHCS + tnut [ENDER3] | assembly |
| 2 | M3x16 BHCS [ENDER3] | part |

### Unresolved in CAD

| Qty | Component | Kind |
|----:|-----------|------|
| 2 | Component3086 | part |
| 1 | Component3037 | part |
| 1 | Component3087 | assembly |
| 1 | Component3088 | part |
| 1 | Component3091 | part |
| 1 | Component3165 | part |

### Printed parts, brackets & sub-assemblies

| Qty | Component | Kind |
|----:|-----------|------|
| 2 | Y_belt_clamp | part |
| 2 | Z_motor_spacer_new v1 | assembly |
| 1 | Back_bracket_L | assembly |
| 1 | Back_bracket_L (Mirror) | assembly |
| 1 | bracket | part |
| 1 | bracket (Mirror) | part |
| 1 | Corner_ brackets | assembly |
| 1 | Ender3 pro Frame | assembly |
| 1 | mgn mod | assembly |
| 1 | Spoilboard | part |
| 1 | x chain mount | part |
| 1 | x_belt_clamp | assembly |
| 1 | xy joints_3x Xaxis rods | assembly |
| 1 | xy_2hole | assembly |
| 1 | xy_2hole (Mirror) | assembly |
| 1 | xz_gantry_plate 3x rods | part |
| 1 | y chain mount | part |
| 1 | y chain mount back | part |
| 1 | Z_axis_150mm | assembly |

## Where the source names disagree

Recorded, not resolved. In each case the CAD carries two names for one thing
and they do not match. Nothing below is a conclusion about the real geometry.

**1. Leadscrew nut: TR8x4 vs TR8x8**
Product name `Anti-Backlash_Nut_TR8x4`; label on all three placements
`Two-trees Anti-Backlash TR8x8 v1`. A TR8x4 has a 4 mm lead, a TR8x8 an 8 mm
lead.

**2. Y rail: 360 vs 300**
Sub-assemblies labelled `mgn12h 360 Y`; the rail product inside each is
`MGN12 Rail - 300mm` - the same product the 300 mm X rails use.

**3. Screw head: SHCS vs BHCS**
Several fasteners carry product name `M3x10 SHCS` under the label
`M3x10 BHCS [BUY]`. Socket head and button head differ in head diameter and
height.

**4. 7 occurrences carry no usable name**
Rows reading `ComponentNNNN` were never named by the author; the CAD says
nothing further about them.

Separately, some components carry the browser label `(Unsaved)` - Fusion's
placeholder for anything never saved to the cloud - but do still have a real
product name underneath. Where that name is meaningful this document uses it,
which is why the MGN12H carriages tally as carriages rather than as eight
anonymous `(Unsaved)` rows.

**5. Endstop internals are modelled separately**
`Contacts`, `Lever`, `Plunger` and `Switch Body` are the modelled interior of
the D2F-L microswitches - four sub-parts per switch, not four separate
components.

**6. Spindle mount collar diameter**
The label decodes to `Ø65mm router clamp V1`. The product name is
`Supporto mandrino` (Italian: spindle support) and carries no diameter.

## How this sits next to the other docs in this folder

Each covers a different scope, so their numbers are not comparable.

| Document | Scope |
|---|---|
| [`BOM.md`](BOM.md) | The **belted** MGN build - lists GT2 belts and 20T pulleys, continues to v-wheel carriage prep. |
| **This document** | The **leadscrew** branch of the BETA CAD only. No belts, no pulleys. |
| [`references/printables-chauk-e3cnc-mgn-mod.md`](references/printables-chauk-e3cnc-mgn-mod.md) | Chauk's threaded-rod remix - **descended from this mod**, with its own changes (350 mm rails, Z moved 2 mm). Because it is downstream, where its component names agree with this CAD they are inherited from it, not independently arrived at. |
| [`references/discord-notes.md`](references/discord-notes.md) | One builder's log against that remix, with his own profile substitutions. |

For scale: this CAD branch places 10 MGN12H carriages and 2 MGN12C; Chauk's
remix calls for 6 and 6; `BOM.md` asks for 70 M5x16 across a whole machine
where this branch places 30. Chauk's page also notes *"There is no official
BOM for this build."*

## What this document cannot tell you

It was built by reading the STEP file's assembly graph - names, nesting, and
placement counts. That is all genuinely in the file.

It contains **no measurements**. Nothing here was derived from the geometry:
not a length, not a hole spacing, not a clearance, not a fit. Where a
dimension appears above it is because the author typed it into a component
name - and component names are exactly the thing this document has just shown
to be unreliable.

The geometry to answer those questions is in the file; it simply has not been
read here.
