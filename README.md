# crb-vdc

This repo contains an orthomosaic, in GeoTIFF format, from a drone survey of coconut palms at Villa Del Carmen, Yona, Guam. 
Images were taken at 400 feet above ground with the camera pointed straight down.
The drone was piloted by Jonelle N. Sayama and Keanno Lawrence A. Fausto, members of the [University of Guam Drone Corps](https://www.uog.edu/nasa-guam-space-grant/uog-drone-corps) and the orthomosaic was made by Jonelle N. Sayama using Drone Deploy. 

Many of the coconut palms in the orthomosaic show damage from coconut rhinoceros beetle (CRB), *Oryctes rhinoceros*, visible as v-shaped cuts to fronds. We plan to use the orthomosaic to develop deep learning models trained to detect and quantify CRB damage. 

[![CC BY-NC-SA 4.0][cc-by-nc-sa-image]][cc-by-nc-sa]
This repository is licensed under a [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License][cc-by-nc-sa].
You are free to use the data providing you acknowledge [University of Guam Drone Corps](https://www.uog.edu/nasa-guam-space-grant/uog-drone-corps) pilots. Something like *"Thanks to University of Guam Drone Corps pilots Jonelle N. Sayama and Keanno Lawrence A. Fausto for providing drone imagery"* will suffice.

[cc-by-nc-sa]: http://creativecommons.org/licenses/by-nc-sa/4.0/
[cc-by-nc-sa-image]: https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png

### Technical Notes

The original GeoTIFF file is larger than GitHub's recommended maximum file size (50 MB), so it was split into smaller geoTIFFS with a raster size of 1000 x 1000 pixels
using Python code contained in a Jupyter Notebook, **split_geotiff.ipynb**.  These smaller geoTIFFs are stored in the **tiles** folder. 
In addition, a **virtual raster file (vdc.vrt)** is built. This is simply a text file in **xml** format which provides an index of the tiles.
**vdc.vrt** can be opened by QGIS and it greatly speeds up loading and visualizing all the tiles displayed as a mosaic.

If needed, the **vrt** file can also be used to merge all of the geoTIFF tiles back into a single, large geoTIFF:
```
gdal.Translate('vdc2.tif', 'vdc.vrt')
```

### TODO
* Create a **jpg** folder and populate it with the tiles converted from geoTIFF to jpg.
* See if the Jupyter notebooks will run on Colab.
