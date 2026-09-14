# GCKontrol and GCAir FMI compatibility and examples exported FMUs

<img width="1504" height="666" alt="02_世冠科技_标准Logo_彩色版_白底" src="https://github.com/user-attachments/assets/d3b0526c-e19a-491e-9bbc-d72c5207ece7" />

# Global Crown Technology
https://www.globalcrown.com.cn

GCKontrol and GCAir are modeling and simulation tools developped by Global Crown Technology. This repository contains FMI compatibility tests and exported FMU examples.

********
Please report failures and problems in the "issues" page of this repository. 
********

# GCKontrol FMI Export compatibility information and examples

The exported FMUs contain c source code , win64 and lnx64 binaries. The FMU can be recompiled for other platforms. 
FMUs are sorted in folders for various GCKontrol and FMI versions. We provide input csv file and reference output csv file. 

The examples FMUs provided were imported and tested succesfully with FMPy 0.3.15, FMPy 0.3.31 , GCAir 10.2.1 and GCKontrol 10.2.1.


# GCKontrol and GCAir FMI import compatibility information


## Reference FMUs
https://github.com/modelica/Reference-FMUs

### GCAir

GCAir V10.2.1. 

| FMU           | FMI version | CS  | ME  | Notes |
|---------------|:-----------:|:---:|:---:|-------|
| BouncingBall  | FMI 3.0     | ✅  | —   | |
| Clocks        | FMI 3.0     | ❌  | —   | Clocks not supported |
| Dahlquist     | FMI 3.0     | ✅  | —   | |
| Feedthrough   | FMI 3.0     | ✅  | —   | |
| Resource      | FMI 3.0     | ✅  | —   | |
| Roberts       | FMI 3.0     | ✅  | —   | |
| Stair         | FMI 3.0     | ✅  | —   | |
| StateSpace    | FMI 3.0     | ❌  | —   | structural parametrers not supported |
| VanDerPol     | FMI 3.0     | ✅  | —   | |
| BouncingBall  | FMI 2.0     | ✅  | ✅  | |
| Dahlquist     | FMI 2.0     | ✅  | ✅  | |
| Feedthrough   | FMI 2.0     | ✅  | ✅  | limitation : string type not handled |
| Resource      | FMI 2.0     | ✅  | ✅  | |
| Stair         | FMI 2.0     | ✅  | ✅  | |
| VanDerPol     | FMI 2.0     | ✅  | ✅  | |

### GCKontrol

GCKontrol 10.2.1

| FMU           | FMI version | CS  | Notes |
|---------------|:-----------:|:---:|-------|
| BouncingBall  | FMI 3.0     | ✅  | |
| Clocks        | FMI 3.0     | ❌  | Clock variables not supported |
| Dahlquist     | FMI 3.0     | ✅  | |
| Feedthrough   | FMI 3.0     | ❌  | String/Boolean/Enumeration types not supported |
| Resource      | FMI 3.0     | ❌  | known bug in 10.2.1， will be fixed |
| Roberts       | FMI 3.0     | ✅  | reference CSV mismatch, verified via conservation law instead |
| Stair         | FMI 3.0     | ✅  | simulation limited to ≤5 s |
| StateSpace    | FMI 3.0     | ✅  | |
| VanDerPol     | FMI 3.0     | ✅  | |
| BouncingBall  | FMI 2.0     | ✅  | |
| Dahlquist     | FMI 2.0     | ✅  | |
| Feedthrough   | FMI 2.0     | ❌  | String/Boolean/Enumeration types not supported |
| Resource      | FMI 2.0     | ✅  | |
| Stair         | FMI 2.0     | ✅  | |
| VanDerPol     | FMI 2.0     | ✅  | |

✅ tested and passed &nbsp;|&nbsp; ❌ failed &nbsp;|&nbsp; — not tested (interface not offered by this FMU/tool)


## Dymola 
https://github.com/CATIA-Systems/dymola-fmi-compatibility/tree/main

Tested with the `CoupledClutches` example FMUs exported from Dymola 2026x (`FMUs_othertools/dymola-fmi-compatibility-main/2026x, 2025-10-10/`).

### GCAir

GCAir supports both CS and ME, for FMI 1.0, 2.0, 3.0

| FMU                              | CS  | ME  |
|-----------------------------------|:---:|:---:|
| CoupledClutches_fmi1_Cvode.fmu    | ✅  | —   |
| CoupledClutches_fmi1_Dassl.fmu    | ✅  | —   |
| CoupledClutches_fmi1_Ida.fmu      | ✅  | —   |
| CoupledClutches_fmi1_Inline.fmu   | ✅  | —   |
| CoupledClutches_fmi2_Cvode.fmu    | ✅  | ✅  |
| CoupledClutches_fmi2_Dassl.fmu    | ✅  | —   |
| CoupledClutches_fmi2_Ida.fmu      | ✅  | ✅  |
| CoupledClutches_fmi2_Inline.fmu   | ✅  | —   |
| CoupledClutches_fmi3_Cvode.fmu    | ✅  | ✅  |
| CoupledClutches_fmi3_Dassl.fmu    | ✅  | —   |
| CoupledClutches_fmi3_Ida.fmu      | ✅  | ✅  |
| CoupledClutches_fmi3_Inline.fmu   | ✅  | —   |

### GCKontrol

GCKontrol import was only tested against the FMI 2.0 FMUs. 

| FMU                              | CS  |
|-----------------------------------|:---:|
| CoupledClutches_fmi2_Cvode.fmu    | ✅  |
| CoupledClutches_fmi2_Dassl.fmu    | ✅  |
| CoupledClutches_fmi2_Ida.fmu      | ✅  |
| CoupledClutches_fmi2_Inline.fmu   | ✅  |

✅ tested and passed &nbsp;|&nbsp; — interface not offered by this FMU.

## MapleSim
https://github.com/Maplesoft-fmigroup/MapleSim_FMI

Tested with the MapleSim 2024 exported FMUs.

### GCAir

| Model                  | FMI version | CS  | ME  |
|------------------------|:-----------:|:---:|:---:|
| CoupledClutches        | FMI 2.0     | ✅  | ✅  |
| CoupledClutches        | FMI 3.0     | ✅  | —   |
| ControlledTemperature  | FMI 2.0     | ✅  | ✅  |
| ControlledTemperature  | FMI 3.0     | ✅  | —   |

✅ tested and passed &nbsp;|&nbsp; — not tested

### GCKontrol

| Model           | FMI version | CS  |
|-----------------|:-----------:|:---:|
| CoupledClutches | FMI 2.0     | ✅  |
| CoupledClutches | FMI 3.0     | ✅  |
| Rectifier       | FMI 2.0     | ✅  |
| SlidingCrank    | FMI 3.0     | ✅  |

✅ tested and passed


## Mworks Sysplorer
https://github.com/TongYuan-MC/fmus/tree/main

Tested with the MWorks Sysplorer 2025b exported FMUs.

### GCAir

| Model           | FMI version | CS  | ME  |
|-----------------|:-----------:|:---:|:---:|
| CoupledClutches | FMI 2.0     | ✅  | ✅  |
| BouncingBall    | FMI 1.0     | ✅  | ✅  |
| BouncingBall    | FMI 2.0     | ✅  | ✅  |
| DFFREG          | FMI 1.0     | ✅  | ✅  |
| DFFREG          | FMI 2.0     | ✅  | ✅  |

✅ tested and passed

### GCKontrol

| Model           | FMI version | CS  |
|-----------------|:-----------:|:---:|
| CoupledClutches | FMI 2.0     | ✅  |
| BouncingBall    | FMI 2.0     | ✅  |
| DFFREG          | FMI 2.0     | ✅  |

✅ tested and passed


## dSPACE TargetLink
https://www.dspace.com/en/pub/home/support/supvers/supverscompm/fmicompatibility/fmi-cross-check-targetlink.cfm

Tested with the TargetLink 24.1 exported FMUs. These FMUs are CoSimulation only and contain
the C source code, plus binaries for Linux 64-bit, Windows 64-bit and Windows 32-bit.

### GCAir

| FMU                      | FMI version | CS  | ME  |
|--------------------------|:-----------:|:---:|:---:|
| Fmucontroller            | FMI 2.0     | ✅  | —   |
| Fmufuelratecontroller    | FMI 2.0     | ✅  | —   |
| FmuTL_VelocityController | FMI 2.0     | ✅  | —   |
| controller               | FMI 3.0     | ✅  | —   |
| fuelratecontroller       | FMI 3.0     | ✅  | —   |
| TL_VelocityController    | FMI 3.0     | ✅  | —   |

✅ tested and passed &nbsp;|&nbsp; — not tested
