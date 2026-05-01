# aerobeat-input-joycon-hid

**Date:** 2026-05-01  
**Status:** Complete  
**Agent:** Chip 🐱‍💻

---

## Goal

Align `aerobeat-input-joycon-hid` with the locked AeroBeat v1 downscope so the repo clearly presents JoyCon HID as future/deprioritized experimentation rather than current official gameplay input.

---

## Overview

This repo sits in the future-support edge of the AeroBeat input/platform matrix. The work for this pass stays intentionally light: correct the README, plugin metadata, hidden testbed manifest, and other obvious repo-truth surfaces so they match the downscoped docs stance.

The current official AeroBeat v1 product claim is camera-driven Boxing and Flow on PC first. JoyCon HID remains useful as preserved architecture and future experimentation, but the repo should not imply equal-status gameplay parity or current shipping support.

---

## REFERENCES

| ID | Description | Path |
| --- | --- | --- |
| `REF-01` | Parent input/platform coordination plan | `/home/derrick/.openclaw/workspace/projects/openclaw-chip/.plans/2026-05-01-aerobeat-input-platform-downscope-pass.md` |
| `REF-02` | Downscoped docs source of truth | `/home/derrick/.openclaw/workspace/projects/aerobeat/aerobeat-docs` |
| `REF-03` | JoyCon docs API page | `/home/derrick/.openclaw/workspace/projects/aerobeat/aerobeat-docs/docs/api/inputs/joycon-hid/index.md` |
| `REF-04` | Input-strategy docs truth | `/home/derrick/.openclaw/workspace/projects/aerobeat/aerobeat-docs/docs/gdd/input-system/agnostic-input.md` |
| `REF-05` | Owning repo | `/home/derrick/.openclaw/workspace/projects/aerobeat/aerobeat-input-joycon-hid` |

---

## Tasks

### Task 1: Audit and align repo truth

**Bead ID:** `oc-92i`  
**SubAgent:** `primary`  
**Role:** `coder`  
**References:** `REF-01`, `REF-02`, `REF-03`, `REF-04`, `REF-05`  
**Prompt:** Claim the assigned bead, audit the repo against the downscoped AeroBeat docs truth, implement the required alignment changes, run relevant validation, commit/push to `main`, and leave concise QA handoff notes.

**Folders Created/Deleted/Modified:**
- `.plans/`
- `.testbed/`

**Files Created/Deleted/Modified:**
- `README.md`
- `plugin.cfg`
- `.testbed/addons.jsonc`
- `.testbed/project.godot`
- `.testbed/tests/test_example.gd`
- `.plans/2026-05-01-input-joycon-hid-downscope-alignment.md`

**Status:** ✅ Complete

**Results:**
- Rewrote the repo README so JoyCon HID is described as future-facing experimentation/hardware research rather than an official v1 gameplay path, while explicitly reaffirming the current camera-first Boxing/Flow product truth from `REF-03` and `REF-04`.
- Updated `plugin.cfg` to carry future-support wording directly in the plugin name/description so package metadata no longer reads like an active shipping input driver.
- Updated `.testbed/addons.jsonc` from the older transition-era `aerobeat-core` dependency label to the current `aerobeat-input-core` lane naming and clarified that the hidden workbench exists for future JoyCon experimentation.
- Renamed the hidden testbed app surface to `AeroBeat JoyCon HID Input Testbed` and tightened the repo-local smoke test so it asserts the plugin description keeps the downscoped v1 truth visible.
- Validation completed successfully:
  - `cd .testbed && godotenv addons install`
  - `godot --headless --path .testbed --import`
  - `godot --headless --path .testbed --script addons/gut/gut_cmdln.gd -gdir=res://tests -ginclude_subdirs -gexit`
- **QA handoff notes:** verify the README/plugin wording consistently reads as future support only, confirm the hidden testbed restores `aerobeat-input-core` + GUT cleanly, and treat passing validation here as internal repo coherence rather than proof of official JoyCon gameplay support.

---

## Final Results

**Status:** ✅ Complete

**What We Built:** Completed a narrow truth pass for `aerobeat-input-joycon-hid` so its human-facing docs, plugin metadata, testbed manifest, and smoke tests all present JoyCon HID as preserved future experimentation instead of current AeroBeat v1 gameplay support.

**Reference Check:** Satisfied `REF-03` and `REF-04` by aligning the repo to the docs truth that official v1 gameplay input is camera-only, while JoyCon stays documented as future support. The repo-local surfaces no longer claim official JoyCon parity.

**Commits:**
- `Downscope JoyCon HID repo truth surfaces`

**Lessons Learned:** Even a very small future-support repo still carries product-truth risk in metadata and hidden workbench files, not just the README. The testbed manifest and plugin description were both important truth surfaces in this pass.

---

*Completed on 2026-05-01*
