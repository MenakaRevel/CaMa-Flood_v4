# Update Note: CaMa-Flood v4.2

Current official release on webpage is v4.20
Latest GitHub branch (master)  is v4.20

## Version 4.0x
New code structure and improved topography

### Update in v4.00 (compared to v3.6)
- Major Version Update
- New code structure for more flexible model use
- Topography data updated to **MERIT DEM / MERIT Hydro**

### Update in v4.01 (2021.03.31)
#### Importants changes for all users
- **GitHub** code management started.
- **bugfix** in map/src/src_param (src_region) /**generate_impmat.F90**.
- **LBITSAFE for bit-identical simulation was removed**. DNoAtom should be speficied in Mkinclude for bit-identical simulations by avoiding OMP Atomic calculation.
- Sample script for result visualization and validation: etc/validation
#### Changes related to some developpers 
- ILS additional code integrated (for use in U-Tokyo Integrated Land Simulator)
- Reservoir module (test version, no support): CTRL_DAMOUT_MOD, etc/reservoir_operation/  

### Update in v4.02 (2021.07.20)
#### Changes related to some developpers 
- Runoff nearest neighbour interporlation reactivated.
- Flood stage calculation for vector processor (Earth Simulator) 

### Update in v4.03 (2021.07.28)
#### Importants changes for all users
- bug fix on water storage budget (calc_stonxt)
#### Changes related to some developpers 
- Downstream dynamic sea level boundary scheme, bug fix & improvement (etc/sealev_boundary)

## Update in v4.04 (2021.12.24)
### Changes related to some developpers 
- MPI parallelization (etc/options_HPC)
- Improve initialization efficiency

### Update in v4.05 (2022.3.14)
#### Changes related to some developpers 
- Levee scheme implemented (etc/levee_test)
- Water balance log for flood stage calculation

### Update in v4.06 (2022.4.8)
#### Changes related to some developpers 
- Computationally efficient levee scheme
- This version for internal development, so not released.

### Update in v4.07 (2022.10.20)
#### Changes related to some developpers 
- Single precision mode activated. Many physics codes are modified for Single Precision mode efficiency.
- (Some codes for EFMWF/IFS system was updated)

## Version 4.1x
Better computational efficienty

### Update in v4.10 (2023.01.02)
#### Changes related to some developpers 
- Updates on Single Precision Mode, which is now used as default. (large change in codes)
- Double Precision Restart is now treated as default.
- Sediment scheme (tentative) is integrated
- (Some codes for ILS couping were updated)

### Update in v4.12 (2023.10.23)
#### Changes related to some developpers 
- Updates on reservoir operation (new parameter file format, better method for allocation)
- Runoff undef value treatment in cmf_utils

## Version 4.2x
Reservoir operation recommended as default scheme

### Update in v4.20 (2024.4.19)
#### Changes related to some developpers 
- Updates on reservoir operation (parameter estimation in map/src/src_dam/)
- Better netCDF map treatment
- Better downscaling considering tributary inundation

### v4.21 is internal release 

### Update in v4.22 (tentative, 2024.Autumn)
#### Changes related to some developpers 
- Output Variable OUTFLW was wrongly set as "OUTFLW = RIVOUT + FLDOUT + PTHOUT". It was corrected as "OUTFLOW = RIVOUT + FLDOUT" (main river network discharge)
- Definition of output variable PTHOUT was updated. It is now "net outflow-inflow through bifurcation channels at each grid".
- Improved numerical stability of bifurcation flow scheme, by updating Flow Limitter in CALC_INFLOW
- Tentative Version of Tracer Scheme was developped.

### Update in v4.23 (2024.11.25)
#### Improved stability
- New storage change limitter for stability improvement

### Update in v4.23 (2025.Sep)
#### Improved stability
- Speed up by SIMD, Quasi-Sparse-Matrix
