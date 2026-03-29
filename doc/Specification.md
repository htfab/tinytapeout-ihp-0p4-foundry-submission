# Tiny Tapeout IHP 0p4 - Design Specification

## 1. Overview

Tiny Tapeout IHP 0p4 is an experimental multi-project carrier (MPC) chip designed
for the IHP SG13CMOS5L 130nm CMOS process. It enables educational and research
access to silicon fabrication by aggregating many small user designs onto a single die.

## 2. Process Technology

- **Foundry:** IHP (Leibniz-Institut fuer innovative Mikroelektronik)
- **Process:** SG13CMOS5L (130nm CMOS, 5 metal layers)
- **Metal stack:** 5 thin metals (no thick top metals)
- **PDK version:** `2dcbf0761b18342baeb85b0f5a94e2bec22db496`

## 3. Physical Design

| Parameter                  | Value                         |
| -------------------------- | ----------------------------- |
| Die width                  | 3600 um                       |
| Die height                 | 5000 um                       |
| Grid dimensions            | 12 columns x 20 rows          |

## 4. Multiplexer Architecture

### 4.1 tt_ctrl (Address Controller)

Active-low select chain that routes control signals to the mux array.

### 4.2 tt_mux (Multiplexer Array)

Connects user project I/Os to the chip's external pins based on the
selected address.

### 4.3 tt_top (Top-Level Wrapper)

Instantiates tt_ctrl, tt_mux grid, padring, and user project macros.

## 5. Verification

- **DRC:** KLayout (IHP SG13CMOS5L rules) - PASS
- **LVS:** Netgen (SPICE extraction via Magic) - PASS ("Circuits match uniquely")

## 6. EDA Tools

| Tool        | Purpose                                 |
| ----------- | --------------------------------------- |
| LibreLane   | RTL-to-GDS compilation flow             |
| Yosys       | Logic synthesis                         |
| OpenROAD    | Floorplanning, placement, routing, STA  |
| Magic       | SPICE extraction, DRC                   |
| Netgen      | LVS                                     |
| KLayout     | DRC, density check, GDS streamout, fill |
