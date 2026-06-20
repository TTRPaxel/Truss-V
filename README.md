# Truss-V // FPGA Edge Compute Platform

A custom dual-layer, high-speed hardware platform designed around a Xilinx/AMD Spartan-7 FPGA architecture. Optimized for independent edge computing, layout routing constraints passing 100% DRC validation. 

![Truss-V 3D Render](fpga-edge-compute.png)

---

## Technical Specifications & Topology

### 1. Computational Core (Who is Who)
* **Brain:** AMD/Xilinx Spartan-7 XC7S15 FPGA (FTGB196 footprint).
* **Memory:** HyperRAM parallel data bus for high-bandwidth, low-latency temporary storage execution.
* **Storage Pipeline:** Dual-stage non-volatile memory structure for hardware configuration bitmaps and localized boot code execution.
* **Power Topology:** Multi-stage isolated power tree feeding specific core rails:
    * `+5.0V` External/USB Input
    * `+3.3V` Auxiliary / I/O Rail
    * `+1.0V` Core Logic VCC Rail

### 2. Interface Layout (Who is Where)
* **Power/Data Entry:** GCT USB4105 USB-C connector (`J2`) located at the bottom edge. Ground planes directly stitched around mounting pins for structural mechanical stability.
* **Main Expansion:** Heavy multi-pin ribbon bus header (`J1`) routing broken-out general-purpose I/O channels straight from the FPGA fabric.
* **Peripheral Interface:** Auxiliary ribbon header (`J4`) on the right margin handling dedicated secondary bus lanes.
* **Diagnostics:** Onboard status indicator LED (`D1`) tied directly to a dedicated testing net.

---

## Design State
* **Layers:** 2 Layers (Front Copper `F.Cu` / Bottom Copper `B.Cu`).
* **DRC Status:** 100% Passed. 0 Errors, 0 Warnings. 
* **Hole Clearance Note:** Minimal mechanical-to-electrical pad clearance tightly set to 0.18mm to perfectly accommodate the GCT USB-C footprint manufacturer specifications without causing shorts.

## License
Licensed under the open-source MIT License. You can fork it, modify it, or use it commercially, but copyright attribution stays with the author. See the LICENSE file for details.
