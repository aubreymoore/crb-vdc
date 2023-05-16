## Splitting the GeoTIFF into chunks
```
mkdir chunks
split -b 40M <filename> chunks/
rm <filename>
```

## GeoTIFF metadata
*  resolution is 0.57 in/px (= 1.4478 cm/px)
* coordinate reference system is WG@ 84 / UTM zone 55N (EPSG:32655). This means that longitude is expressed in meters to the east of 144 degrees and latitude is expressed as meters north of the equator.