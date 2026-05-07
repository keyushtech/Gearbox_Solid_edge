# Stratos Gearbox — CAD Assembly

A multi-part mechanical gearbox designed in **Siemens Solid Edge**, consisting of a drive gear, gear train, support structure, and input/output interfaces. The assembly supports both manual (handle) and powered (drill adapter) operation.

---

## Project Structure

```
Stratos_gearbox/
├── Final_assembly.asm       # Top-level Solid Edge assembly file
├── Final_assembly.dft       # 2D draft/drawing file
├── Final_assembly.cfg       # Assembly configuration
└── Parts/
    ├── Drive_gear.par       # Primary input gear
    ├── Large_gear.par       # Large driven gear
    ├── Smal_gear.par        # Small driven gear
    ├── Rod.par              # Shaft / connecting rod
    ├── Handle.par           # Manual operation handle
    ├── Drill_adapter.par    # Power tool input adapter
    ├── Stand.par            # Base/support structure
    ├── Large_spacer.par     # Spacer (large)
    └── Small_spacer.par     # Spacer (small)
```

---

## Components

| Part | File | Description |
|------|------|-------------|
| **Drive Gear** | `Drive_gear.par` | Primary input gear; receives torque from either the handle or drill adapter and initiates the gear train |
| **Large Gear** | `Large_gear.par` | Large driven gear in the gear train; the most geometrically complex part in the assembly |
| **Small Gear** | `Smal_gear.par` | Small driven gear; meshes with the large gear to achieve speed/torque ratio change |
| **Rod** | `Rod.par` | Central shaft that connects and supports rotating gear elements |
| **Handle** | `Handle.par` | Manual input interface; allows hand-cranking the gearbox |
| **Drill Adapter** | `Drill_adapter.par` | Alternate input interface; couples a power drill to the drive gear for motorized operation |
| **Stand** | `Stand.par` | Base structure that mounts and supports the entire assembly |
| **Large Spacer** | `Large_spacer.par` | Maintains axial spacing between larger components on the shaft |
| **Small Spacer** | `Small_spacer.par` | Maintains axial spacing between smaller components |

---

## Assembly Overview

The gearbox operates on a simple gear reduction principle:

1. **Input** — Torque is applied at the **Drive Gear** via the **Handle** (manual) or **Drill Adapter** (powered).
2. **Gear Train** — The Drive Gear meshes with the **Large Gear**, which in turn couples to the **Small Gear**, producing a speed and torque transformation across the stages.
3. **Shaft & Spacing** — The **Rod** serves as the central axis, with **Large** and **Small Spacers** ensuring correct axial positioning and preventing gear-to-gear contact where not intended.
4. **Support** — The **Stand** provides a rigid base, holding all rotating components in alignment.

---

## File Formats

| Extension | Format | Purpose |
|-----------|--------|---------|
| `.asm` | Solid Edge Assembly | Defines part relationships, constraints, and the full assembly tree |
| `.dft` | Solid Edge Draft | 2D engineering drawing with views, dimensions, and annotations |
| `.cfg` | Configuration file | Stores assembly display/configuration settings |
| `.par` | Solid Edge Part | Parametric 3D solid model for each individual component |

> **Note:** These files are native to **Siemens Solid Edge** and require Solid Edge (ST or SE version) to open and edit. For viewing only, Solid Edge Viewer (free) can be used. Files can also be exported to STEP (`.stp`) or IGES (`.igs`) for use in other CAD platforms.

---

## Software Requirements

- **Siemens Solid Edge** (any recent version) — for full editing and assembly management
- **Solid Edge Viewer** — for read-only viewing (free download from Siemens)
- Alternatively, export to **STEP / IGES / STL** for use in Fusion 360, SolidWorks, FreeCAD, etc.

---

## Opening the Assembly

1. Extract the ZIP archive, preserving the folder structure.
2. Open Solid Edge and navigate to `Stratos_gearbox/`.
3. Open `Final_assembly.asm` — Solid Edge will automatically resolve all part references from the `Parts/` subfolder.
4. To view the 2D drawing, open `Final_assembly.dft`.

> **Important:** Keep the `Parts/` folder in the same directory as `Final_assembly.asm`. Moving parts to a different location will break assembly references and require re-linking.

---

## Notes

- The part file `Smal_gear.par` contains a typo in its filename (missing 'l'). This is intentional/as-is — renaming it will break the assembly reference unless the `.asm` file is updated accordingly.
- The original files were authored on macOS (paths reference `\\Mac\Home\Desktop\College\Temp\GEARBOX\`), so re-linking may be required when opening on a Windows machine for the first time.
- `__MACOSX/` metadata folders in the ZIP are macOS artifacts and can be safely ignored.
