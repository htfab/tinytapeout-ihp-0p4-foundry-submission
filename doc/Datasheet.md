# Tiny Tapeout IHP 0p4 - Datasheet

## General Description

Tiny Tapeout IHP 0p4 (TTIHP0p4) is an experimental multi-project carrier chip
fabricated on the IHP SG13CMOS5L 130nm CMOS process. It aggregates 40 independently
designed digital user projects onto a single die using a multiplexer architecture.

## Key Specifications

| Parameter      | Value                      |
| -------------- | -------------------------- |
| Process        | IHP SG13CMOS5L (130nm CMOS)|
| Die size       | 3600 x 5000 um             |
| Tile grid      | 12 x 20                    |
| Top cell       | TT0004                     |
| Supply voltage | 1.2V (digital)             |
| Package        | QFN64                      |

## Architecture

The chip uses a hierarchical multiplexer architecture:

- **tt_ctrl** - Address controller with active-low active select chain
- **tt_mux** - Multiplexer array connecting project I/Os via address selection
- **tt_top** (tt_ihp_wrapper) - Top-level wrapper with padring

User projects are selected by writing an address to the control interface. The
selected project's I/Os are connected to the chip's external pins.

## Pin Description

The chip has the following functional pin groups:

- `clk` - User clock
- `rst_n` - User reset (active low)
- `ui[7:0]` - User input pins
- `uo[7:0]` - User output pins
- `uio[7:0]` - Bidirectional user I/O
- `ctrl_sel_rst_n` - Selection reset (active low)
- `ctrl_sel_inc` - Selection increment
- `ctrl_ena` - Control enable

## Design Flow

Built using the LibreLane open-source RTL-to-GDS flow with:

- Yosys for synthesis
- OpenROAD for place and route
- Custom Python scripts for multiplexer routing
- Magic for parasitic extraction
- Netgen for LVS verification
- KLayout for DRC and GDS generation
