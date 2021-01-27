## Volcanic hazard exacerbated by global warming–driven increase in heavy rainfall
### Jamie I. Farquharson, Falk Amelung
Rosenstiel School of Marine and Atmospheric Science, University of Miami, Miami, FL, USA

Corresponding author: jifarq89@googlemail.com

### This notebook performs all the analysis and plots figures for the research article _Volcanic hazard exacerbated by global warming–driven increase in heavy rainfall_ [submitted]. 

#### Primary data are from nine general circulation models, obtained through Earth System Grid Federation servers, in particular the node hosted by the Lawrence Livermore National Laboratory https://esgf-node.llnl.gov/search/cmip5/.

The .txt files 'climate_mod_files_pr.txt' and 'climate_mod_files_ta.txt' list the files required for the following analyses. To run these code blocks correctly, please ensure that all correct files are downloaded into a directory called ```climate_mods``` in your working directory.

The directory tree should be structured something like this:

```
.
|
+-- __Climate_Forcing_Volcanic_Hazards.ipynb
+-- checkfile.txt
+-- climate_mods
|   |
|   +-- climate_mod_files_pr.txt
|   +-- climate_mod_files_ta.txt
|   +-- pr_Amon_ACCESS1-3_rcp85_r1i1p1_200601-210012.nc
|   :
|   :
|   +-- pr_Amon_NorESM1-M_rcp85_r1i1p1_200601-210012.nc
|   +-- ta_Amon_ACCESS1-3_rcp85_r1i1p1_200601-205512.nc
|   :
|   :
|   +-- ta_Amon_NorESM1-M_rcp85_r1i1p1_200601-210012.nc
|   +-- ScientificColourMaps6
|       |
|       +-- +LICENCE.pdf
|       +-- +README_ScientificColourMaps.pdf
|       +-- +ScientificColourMaps_FabioCrameri.png
|       +-- vik
|       |  |
|       |  +-- vik.txt
|       +-- roma
|            |
|            +-- roma.txt
+-- climate_figures
|   |
|   +-- fig1.png
|   +-- fig1.pdf
|   +-- fig2.png
|   +-- fig2.pdf
|   +-- fig3.png
|   +-- fig3.pdf
|   +-- fig4.png
|   +-- fig4.pdf
|
|
+-- Holocene_volcanoes.csv
+-- Holocene_eruptions.csv
|
+-- data
|   |
|   +-- ACCESS1.3_fmr.npy 
|   +-- CNRM-CM5_fmr.npy 
|   +-- CSIRO-Mk3-6-0_fmr.npy
|   +-- CanESM2_fmr.npy   
|   +-- IPSL-CM5A-MR_fmr.npy
|   +-- MIROC5_fmr.npy
|   +-- MRI-CGCM3_fmr.npy
|   +-- NorESM1-ME_fmr.npy
|   +-- inmcm4_fmr.npy
|
+-- README.md
```
