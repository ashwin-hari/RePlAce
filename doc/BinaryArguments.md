# Usage

## Lef/Def/Verilog (Commercial Format)
    $ ./RePlAce -bmflag <mms/ispd/sb/ibm/etc> -lef tech.lef -lef macro.lef ...  -def <*.def> [-verilog <*.v>] -output <outputLocation> -dpflag <NTU3/NTU4> -dploc <dpLocation> [Options]

* __-bmflag__ : Specify which Benchmark is used
* __-lef__ : \*.lef Location (Multiple lef files supported)
* __-def__ : \*.def Location (Required due to FloorPlan information)
* __-verilog__ : \*.v Location (Optional)
* __-output__ : Specify the Location of Output Results
* __-dpflag__ : Specify which Detailed Placer is Used
* __-dploc__ : Specify the Location of Detailed Placer

## Timing-Driven mode for Lef/Def/Verilog (Commercial Format)
    $ ./RePlAce -bmflag <mms/ispd/sb/ibm/etc> -lef tech.lef -lef macro.lef ...  -def <*.def> -verilog <*.v> -lib lib1.lib -lib lib2.lib ... -timing -clock <clock> -output <outputLocation> -dpflag <NTU3/NTU4> -dploc <dpLocation> [Options]

* __-bmflag__ : Specify which Benchmark is used
* __-lef__ : \*.lef Location (Multiple lef files supported)
* __-def__ : \*.def Location (Required)
* __-verilog__ : \*.v Location (Required)
* __-output__ : Specify the Location of Output Results
* __-dpflag__ : Specify which Detailed Placer is Used
* __-dploc__ : Specify the Location of Detailed Placer

### For Additional Timing-Driven Paramemter

* __-lib__ : \*.lib Location (Multiple lib files supported)
* __-timing__ : Specify the Timing-Driven Placement Mode
* __-clock__ : Specify the Clock Frequency. (e.g. 1ns, -clock 1.0e-9)

## Bookshelf (Academic Format)
    $ ./RePlAce -bmflag <mms/ispd/sb/ibm/etc> -aux <*.aux> -output <outputLocation> -dpflag <NTU3/NTU4> -dploc <dpLocation> [Options]
    
* __-bmflag__ : Specify which Benchmark is used
* __-aux__ : \*.aux Location


## Other Options
### Flow Control
* __-timing__ : Enable Timing-Driven Placement Mode 
* __-skipIP__ : Skip Initial Placement Mode 
* __-onlyGP__ : Only Global Placement Mode
* __-onlyDP__ : Only Detailed Placement Mode
* __-onlyLG__ : Call Detailed Placement in Legalization Mode

### Layout Site Control
* __-newLayout__ : Generate New Sites Based on Given Floorplanned Bounding Box

### Nesterov Control
* __-den__ : Target Density, Floating Number, Default = 1 [0.00,1.00]
* __-bin__ : #bins (in power of 2) for x, y, z Directions, Unsigned Integer[3], Default = 32 32 32
* __-overflow__ : Overflow Termination Condition, Floating Number, Default = 0.1 [0.00, 1.00]
* __-pcofmin__ : µ_k Lower Bound, Float Number, Default = 0.95
* __-pcofmax__ : µ_k Upper Bound, Float Number, Default = 1.05
* __-rancti__ : Max # Global Router Calls and Cell Inflation. No Restore of Cell Size, Keep Increasing, Unsigned Integer, Default = 10
* __-maxinfl__ : Max Cell Inflation for Each Cell Inflation Per Global Router Call. Floating Number, Default = 2.5
* __-inflcoef__ : γ_super, Floating Number, Default = 2.33
* __-filleriter__ : # Filler Only Placement Iterations, Floating Number, Default = 20
* __-stepScale__ : ∆HPWL_REF, Floating Number, Default=346000

### Plot
* __-plot__ : Plot Layout Every 10 Iterations (Cell, Bin, Arrow Plots)

### Router
* __-R__ : Enable Routability flow (currently only supports DAC-2012 and ICCAD-2012 benchmark suites)

### Other
* __-unitY__ : Custom scaledown param for LEF/DEF/Verilog (especially for ASAP N7 library; Recommended: 864)
