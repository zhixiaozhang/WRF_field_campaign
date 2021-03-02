# WRF_field_campaign
Compared with WRF V4.1.1, Following modifications have been conducted in WRF/phys/module_diag_functions.F

1)	Correct the most unstable (MU) layer definition from the max water vapor mixing ratio (w) level to the max equivalent potential temperature (Theta-e) level. Because it is the theta-e rather than mixing ratio is conserved during the dry/moist adiabatic lifting processes.
2)	Correct precipitable water (Pwat) definition from column accumulated mass of water vapor and cloud water to only water vapor. This is based on the AMS glossary https://glossary.ametsoc.org/wiki/Precipitable_water.
3)	Supplement equilibrium level (EL) calculation, which is the highest model level when buoyancy turns from positive to negative.
4)	Save corrected MU layer height, LCL, EL as output variables.
5)	Compute and Save MUCAPE, MUCIN and LFC by refined definitions: MUCAPE and MUCIN are defined as the vertically integrated positive and negative buoyant energy between LCL and EL with the air parcel lifted from MU layer. LFC is defined as the highest separation level when buoyancy turns from negative to positive.
