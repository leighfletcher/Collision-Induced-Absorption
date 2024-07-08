# Collision-Induced-Absorption
Updated collision-induced absorption for hydrogen-rich planetary atmospheres.

Borysow's original fortran codes for many collisional pairs are available on [their website.](https://www.astro.ku.dk/~aborysow/programs/).

The files below serve as Supplemental Information for Orton et al. (2024):

* **h2h2_2500-4000.dat**:  Consolidated table for the H2-H2 collision-induced absorption from 2500-4000 cm-1, including the contribution from the H2-H2 rotovibrational fundamental.

* **h2he_rt.dat**:  Tables for the H2-He collision-induced absorption, from the rototranslational fundamental (far-IR) through to 2400 cm-1.

* **H2H2.lowT.0-1MGfp.f**:  Modified version of Borysow's original H2-H2 code, adjusted to have a variable para-H2 fraction.  Warnings about common blocks have been removed.  This can be compiled with `f95 -o H2H2.lowT.0-1MGfp H2H2.lowT.0-1MGfp.f` or `fifort -o H2H2.lowT.0-1MGfp H2H2.lowT.0-1MGfp.f`

* **h2he_fundamental.dat:** H2-He fundamental output from 2000-8000 cm-1.   Note that in the version available from [Borysow et al. (1988)](https://ui.adsabs.harvard.edu/abs/1988ApJ...326..509B/abstract), the higher-order dipole components 43 and 45 were apparently not accounted for, so the U transitions at 1622 and 2061 cm-1 were missing.

  
