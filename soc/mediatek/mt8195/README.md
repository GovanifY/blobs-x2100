# Firmware list
- mcupm.bin
- sspm.bin

--------------------------------------------------------------------------------
# MCUPM introduction
MCUPM is a hardware module which is used for MCUSYS Power Management.
MCUPM firmware (`mcupm.bin`) is loaded into MCUPM SRAM at system initialization.

## Who uses it
Coreboot will load MCUPM at ramstage. It will copy mcupm.bin to MCUPM SRAM.

## How to load `mcupm.bin`
Use CBFS to load `mcupm.bin`, then set normal boot flag and release software reset pin of MCUPM.

## Return values
No return value.

## Version
`$ strings mcupm.bin | grep "MCUPM firmware"`

--------------------------------------------------------------------------------
# SSPM introduction
SSPM is "Secure System Power Manager" that provides power control in secure domain.
SSPM provides power related features, e.g. CPU DVFS, thermal control, to offload
application processor for security reason.

SSPM firmware is loaded into SSPM SRAM at system initialization.

## Who uses it
Coreboot will load sspm.bin to SSPM SRAM at ramstage.

## How to load `sspm.bin`
Use CBFS to load `sspm.bin`.
No need to pass other parameters to SSPM.

## Return value
No return value.

## Version
`$ strings sspm.bin | grep "SSPM firmware"`

--------------------------------------------------------------------------------
