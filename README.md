# Collision-Induced-Absorption
Updated collision-induced absorption for hydrogen-rich planetary atmospheres.

Borysow's original Fortran codes for many collisional pairs are available on [their website.](https://www.astro.ku.dk/~aborysow/programs/).

The files below serve as Supplemental Information for Orton et al. (2025), and are available via:
[![DOI](https://zenodo.org/badge/825714726.svg)](https://zenodo.org/doi/10.5281/zenodo.12687188 )


## H2-H2
* `H2H2_RT_0-2400cm.zip:` Original data for free-free rototranslational (RT) transitions from [Fletcher et al. (2018)](https://arxiv.org/abs/1712.02813) covering 0-2400 cm-1.

* `H2H2_RT_310-630cm.zip:` Higher-resolution data for free-free RT transitions from [Fletcher et al. (2018)](https://arxiv.org/abs/1712.02813) covering 310-630 cm-1, required to supplement the 0-2400 cm-1 data near the dimer features.

* `H2H2_RT_2500-4000cm.zip:` Newly-calculated RT transitions for H2-H2 calculated over 2500-4000 cm-1 for different para-H2 fractions.

* `h2h2_2500-4000.dat:`  Consolidated table for the H2-H2 collision-induced absorption from 2500-4000 cm-1, including the contribution from the H2-H2 rotovibrational fundamental.

* `H2H2_RVfund_1000-11000cm.zip:` Rotovibrational (RV) fundamental for H2-H2 calculated in two parts (1000-6000 cm-1; 6000-11000 cm-1) using modified version of the code from [Borysow.](https://www.astro.ku.dk/~aborysow/programs/H2H2.lowT.0-1.new.for) - `H2H2.lowT.0-1MGfp.f`.  This code has been adjusted to have a variable para-H2 fraction.  Warnings about common blocks have been removed.  This can be compiled with `f95 -o H2H2.lowT.0-1MGfp H2H2.lowT.0-1MGfp.f` or `ifort -o H2H2.lowT.0-1MGfp H2H2.lowT.0-1MGfp.f`

* NB. H2-H2 [1st](http://www.astro.ku.dk/~aborysow/programs/Zheng2.for) and [2nd](http://www.astro.ku.dk/~aborysow/programs/modelYi03.for) overtones must also be added at shorter wavelengths.

* Note that dimer contributions are additionally needed following [Fletcher et al. (2018)](https://arxiv.org/abs/1712.02813).

## H2-He
* `H2He_RT_0-4000cm.zip:` Rototranslational (RT) H2-He collision induced absorption based on Orton et al. (2024).   

* `H2He_RV_2000-8000cm.zip:` Rotovibrational (RV) fundamental H2-He coefficients calculated for variable para-H2 fraction between 2000-8000 cm-1, based on Orton et al. (2024).  These para-H2 tables are then consolidated into `h2he_rt.dat` from 0-2400 cm-1.

* `h2he_fundamental.dat:` Updated H2-He RV fundamental CIA from 2000-8000 cm-1.   

* NB.  H2-He overtones and hot bands are then added following the original Borysow code [`H2He_all_trans.f`](https://www.astro.ku.dk/~aborysow/programs/h2he_all_trans.for).

## NEMESIS Input Files

Multiple versions of the NEMESIS input files are available, with the following characteristics:
* `mgRT_mgRV_40-280K_dnu*.tab` span 40 to 280K in steps of 10K, and are typically useful for simulations of Ice Giants (T<280 K).
* `mgRT_mgRV_40-400K_dnu*.tab` span 40 to 400K in steps of 15K, and are typically useful for simulations of Gas Giants (T<400 K).
* These tables have a maximum of 1501 spectral points, so the different `dnu` flavours span 0-1500 cm-1, 0-3000 cm-1, 0-6000 cm-1 and 0-15,000 cm-1, respectively. 
* These contain the CIA for all gas pairs (including H2-H2 and H2-He) on grids of temperature, pressure, and separated into 24 para-H2 fractions between 0.25 and 1.0.
  
See the [NEMESIS repository](https://github.com/nemesiscode/radtrancode) for full details

## Notes:

* In the version of the H2-He rotovibrational CIA available from [Borysow et al. (1988)](https://ui.adsabs.harvard.edu/abs/1988ApJ...326..509B/abstract), the higher-order dipole components 43 and 45 were apparently not accounted for, so the U transitions at 1622 and 2061 cm-1 were missing.

  
