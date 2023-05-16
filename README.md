# crb-yona-tiff

This repo contains an orthomosaic, in GeoTIFF format, from a drone survey of coconut palms at Villa Del Carmen, Yona, Guam. 
Images were taken at 400 feet above ground with the camera pointed straight down.
The drone was piloted by Jonelle N. Sayama and Keanno Lawrence A. Fausto, members of the [University of Guam Drone Corps](https://www.uog.edu/nasa-guam-space-grant/uog-drone-corps) and the orthomosaic was made by Jonelle N. Sayama using Drone Deploy. 

Many of the coconut palms in the orthomosaic show damage from coconut rhinoceros beetle (CRB), *Oryctes rhinoceros*, visible as v-shaped cuts to fronds. We plan to use the orthomosaic to develop deep learning models trained to detect and quantify CRB damage. 

[![CC BY-NC-SA 4.0][cc-by-nc-sa-image]][cc-by-nc-sa]
This repository is licensed under a [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License][cc-by-nc-sa].
You are free to use the data providing you acknowledge [University of Guam Drone Corps](https://www.uog.edu/nasa-guam-space-grant/uog-drone-corps) pilots. Something like *"Thanks to University of Guam Drone Corps pilots Jonelle N. Sayama and Keanno Lawrence A. Fausto for providing drone imagery"* will suffice.

[cc-by-nc-sa]: http://creativecommons.org/licenses/by-nc-sa/4.0/
[cc-by-nc-sa-image]: https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png

### Some assembly required

The original GeoTIFF file is larger than GitHub's recommended maximum file size (50 MB), so it was split into 40 MB chunks. Run these command lines to download the repo and reassemble the orthomosaic GeoTIFF file:
```
# download data
git clone https://github.com/aubreymoore/crb-yona-tiff.git

# change to newly created directory
cd crb-yona-tiff

# reassemble chunks
cat chunks/* > Map1_Orthomosaic_export_FriMar31060700467300.tif

# delete chunks
rm -rf chunks

# inspect the orthomosaic using QGIS (optional)
qgis Map1_Orthomosaic_export_FriMar31060700467300.tif
```

If you are using Windows, you should be able to reassemble chunks using this command line (untested):
```
type  chunks\* > Map1_Orthomosaic_export_FriMar31060700467300.tif  
```
# crb-vdc
