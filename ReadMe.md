## Volcanic hazard exacerbated by global warming–driven increase in heavy rainfall
### Jamie I. Farquharson, Falk Amelung
Rosenstiel School of Marine and Atmospheric Science, University of Miami, Miami, FL, USA

Corresponding author: jifarq89@googlemail.com

### This notebook performs all the analysis and plots figures for the research article _Volcanic hazard exacerbated by future global warming–driven increase in heavy rainfall_ [submitted]. 

#### Primary data are from nine general circulation models, obtained through Earth System Grid Federation servers, in particular the node hosted by the Lawrence Livermore National Laboratory https://esgf-node.llnl.gov/search/cmip5/.

The .txt files 'climate_mod_files_pr.txt' and 'climate_mod_files_ta.txt' in the ```rcp85``` folder list the files required for the following analyses. To run these code blocks correctly, please ensure that all correct files are downloaded into a directory called ```climate_mods``` in your working directory.

#### Some notes:
1. I've used Fabio Crameri's colourmaps ```vik``` and ```roma```. These are available at http://www.fabiocrameri.ch/colourmaps.php. Citation: Crameri, F., 2018. Scientific colour-maps. Zenodo. doi: http://doi.org/10.5281/zenodo.1243862.
2. The climate model results are provided as ```.netcdf``` files from https://esgf-node.llnl.gov/search/cmip5/. Users will have to access these independently and ensure they are in the ```climate_mods``` folder. Because there may be issues with versioning and/or corruption, there is a ```compare_checksum``` function defined in ```__Climate_Forcing_Volcanic_Hazards.ipynb```. Running this function will check the user-accessed file contents are the same as those used in the initial processing and analysis. If there is a problem, contact the corresponding author who can provide archived versions of model data.

The directory tree should be structured something like this:

```
.
|
+-- __Climate_Forcing_Volcanic_Hazards.ipynb
+-- __Climate_Forcing_Volcanic_Hazards_cache.ipynb
+-- checkfile.txt
+-- climate_mods
|   |
|   +--rcp85
|   |  |
|   |  +-- climate_mod_files_pr.txt
|   |  +-- climate_mod_files_ta.txt
|   |  +-- pr_Amon_ACCESS1-3_rcp85_r1i1p1_200601-210012.nc
|   |  :
|   |  :
|   |  +-- pr_Amon_NorESM1-M_rcp85_r1i1p1_200601-210012.nc
|   |  +-- ta_Amon_ACCESS1-3_rcp85_r1i1p1_200601-205512.nc
|   |  :
|   |  :
|   |  +-- ta_Amon_NorESM1-M_rcp85_r1i1p1_200601-210012.nc
|   |
|   +--rcp45
|   |  |
|   |  +-- climate_mod_files_pr.txt
|   |  +-- climate_mod_files_ta.txt
|   |  +-- pr_Amon_ACCESS1-3_rcp45_r1i1p1_200601-210012.nc
|   |  :
|   |  :
|   |  +-- pr_Amon_NorESM1-M_rcp45_r1i1p1_200601-210012.nc
|   |  +-- ta_Amon_ACCESS1-3_rcp45_r1i1p1_200601-205512.nc
|   |  :
|   |  :
|   |  +-- ta_Amon_NorESM1-M_rcp45_r1i1p1_200601-210012.nc
|   |
|   +--rcp26
|   |  |
|   |  +-- climate_mod_files_pr.txt
|   |  +-- climate_mod_files_ta.txt
|   |  +-- pr_Amon_CanESM2_rcp26_r1i1p1_200601-210012.ncnc
|   |  :
|   |  :
|   |  +-- pr_Amon_NorESM1-M_rcp26_r1i1p1_200601-210012.nc
|   |  +-- ta_Amon_CanESM2_rcp26_r1i1p1_200601-210012.nc
|   |  :
|   |  :
|   |  +-- ta_Amon_NorESM1-M_rcp26_r1i1p1_200601-210012.nc
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
|   +-- ext_data_fig1.png
|   +-- ext_data_fig1.pdf
|   +-- ext_data_fig2.png
|   +-- ext_data_fig2.pdf
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
|   +-- regionalGradientss.pkl
|   +-- subregionalGradients.pkl
|   +-- rain_url.txt
|   +-- magnetic_susceptibility.csv
|   +-- GISP2.csv
|   +-- speleothem-data.csv
|   +-- standardized_precipitation.csv
|   +-- plawangan_rainfall.csv
|   +-- plawangan_rsam.csv
|   +-- winangun_rainfall.csv
|   +-- GVP_webpages_20210311.tar.gz
|
+-- README.md
```
