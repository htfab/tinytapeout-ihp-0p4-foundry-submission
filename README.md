# Tiny Tapeout IHP 0p4 - IHP Open-Silicon MPW Submission

Experimental multi-project carrier chip for the IHP SG13CMOS5L Open-Silicon MPW March 2026 run.

## Overview

Tiny Tapeout IHP 0p4 is an experimental ASIC that aggregates 40 user-submitted
chip designs onto a single die manufactured on the **IHP SG13CMOS5L** 130nm CMOS process.

- **Category:** Digital
- **Subcategory:** Multi Project Carrier (MPC)
- **Process:** IHP SG13CMOS5L
- **Die size:** 3600 x 5000 um
- **Top cell:** `TT0004`
- **Grid:** 12 x 20 tiles
- **License:** Apache-2.0

## Design Source

The chip design source is at: https://github.com/TinyTapeout/tinytapeout-ihp-0p4

The design flow uses:
- **LibreLane** for RTL-to-GDS compilation
- **Yosys** for synthesis
- **OpenROAD** for place and route
- **Magic** for SPICE extraction
- **Netgen** for LVS verification
- **KLayout** for DRC and GDS streamout

## Physical Verification

LVS was verified during the chip build using Netgen (SPICE extracted via Magic
compared against the Verilog netlist). Result: `Circuits match uniquely.`

DRC is verified via GitHub Actions using the IHP SG13CMOS5L PDK scripts.

## Links

- Source repository: https://github.com/TinyTapeout/tinytapeout-ihp-0p4
- Tiny Tapeout: https://tinytapeout.com
- IHP Open-PDK: https://github.com/IHP-GmbH/IHP-Open-PDK
