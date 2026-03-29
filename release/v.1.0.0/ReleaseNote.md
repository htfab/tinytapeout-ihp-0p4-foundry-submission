# Release v.1.0.0

## Tiny Tapeout IHP 0p4 - Initial Release

**Date:** 2026-03-29
**Process:** IHP SG13CMOS5L

### Release Contents

- `gds/TT0004.oas` - Final chip layout (OAS format) with fill and seal ring
- `netlist/tt_ihp_wrapper.nl.v` - Gate-level Verilog netlist
- `netlist/tt_ihp_wrapper.v` - Powered Verilog netlist

### Verification Status

| Check                 | Status                             |
| --------------------- | ---------------------------------- |
| DRC (KLayout)         | PASS                               |
| Metal density         | PASS                               |
| LVS (Netgen)          | PASS - "Circuits match uniquely"   |

### Design Summary

- Die: 3600 x 5000 um
- Grid: 12 x 20 tiles
- Top cell: TT0004
- Built from: https://github.com/TinyTapeout/tinytapeout-ihp-0p4 (commit e5834cb)
