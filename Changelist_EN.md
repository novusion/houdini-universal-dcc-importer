# 📝 Changelog – Universal DCC Importer

## [2025-08-12] Initial MAX Importer

- **Feature**: Added `max_to_houdini.py` – initial `.MAX → Houdini` geometry-only importer.

- Builds per-mesh node chains, merges into `OUT_MERGED`.

- Adds point attributes: `name`, `srcfile`; packed transfer of attributes except `N`.

- Reads input path from `/obj/CONTROL.load_file`.

- **Limitations**:  
  – Materials and UVs not yet supported.  
  – Normals rebuilt inside Houdini.  
  – No hierarchy/USD export yet.

---

## [2025-08-12] MAX Importer Refinement

- Polished first version of `.MAX` importer.

- Improved stability of mesh extraction from OLE2 format.

- Ensured consistent polygon (verts/faces) rebuild for idempotent usage.

- Prepared infra for upcoming UV/material support.

---

## [2025-08-15] Maya Importer – First Implementation

- Added `maya_to_houdini.py`, first iteration of `.MB → Houdini` importer.

- Correctly extracts geometry (faces + meshes).

- Introduced per-file GEO node creation.

- Added caching mechanism for faster reloads.

- Known limitation: transforms and matrix data not yet mapped.

---

## [2025-08-15] Maya Importer Update

- Updated Maya importer to:
  
  - Create GEO node with **filename-based naming**.
  
  - Read all faces and meshes.
  
  - Fixed missing geometry cases.

- Improved cache file handling.

---

## [2025-08-15] Maya Importer Fix

- Fixed regression with `.MB` file import (missing `geo` creation).

- Ensured consistent caching of imported data.

- Stability improvements for larger scenes.

---

## [2025-08-15] Internal Script Updates

- General script cleanup and minor bug fixes.

- Refactored naming and rebuild process (`_ensure_parent_geo_for_file`).

# Next Steps

- UVs and material assignment (both MAX and Maya).

- Smoothing groups, proper normals.

- Scene hierarchy preservation.

- USD/FBX export integration.

- Packaging as Houdini Digital Asset (HDA) with license/trial support.
