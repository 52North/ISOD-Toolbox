# ISOD Toolbox version 1.4

This release contains some new resources. To ensure proper operation, all internet links have been checked and modified if the URLs or the products have changed. Please note that this version has new license and readme files.
Changes

In the XML version 1.4 of the ISOD toolbox a number of additional routines are added, such as the import and radiometric calibration of LANDSAT 8, partial import of large GEOTIF and SHAPE files, NOAA STAR Vegetation products (time series), CHIRPS global rainfall, POWER and CPC Global Forecasting System.

Landsat 8 product from USGS:

- Geotif import, imported as UInt32
- Radiometric calibration implemented:
        DN to Radiance
        Radiance to Reflectance, corrected for sun angle
        Radiance to Temperature, for bands 10 and 11
- Using the parameters from the header file (*MTL_txt)
  PDF document is included describing the procedure

Partial import of large GEOTIF and SHAPE files, using GDAL_Translate and OGR2OGR:

- Using gdalinfo and ogrinfo to obtain map extent
- Subsequent import of TIF file based on user defined map extent
- Import of partial SHAPE file using the user defined map extent to clip the output vector file. The import is only possible if the map layer name is identical to the shape file name!

For both routines use is made of powershell based sub menu’s. The ps1 files are situated in the respective \toolbox_startscript sub directories (here \Landsat8 and \shp_tif_import).
Additions

- Added routine to visualize the latest NOAA CPC Forecasts from the Global Forecasting System (GFS) under the Web Mapping Services.
    Added routine to retrieve and process CHIRPS pentad and monthly rainfall.
    Added routine to retrieve and process JRC – MARS ECMWF based meteorological data: rainfall, temperatures, ETO and Radiation.
    Added routine to retrieve and process time series of NOAA STAR Vegetation products, like Smoothed NDVI, Vegetation Condition Index, Smoothed Brightness Temperature, Vegetation Health Index as well as Climatology for the NDVI and Brightness Temperature.
    Added link to Climatology Resource for AgroClimatology (POWER), under Web Mapping Services

Some routines have been adapted to reflect appropriate import due to changes in the data provision, such as:

- GWADI rainfall: new server address;
- CMORPH 8 km 30 minutes and 0.25 degrees 3 hourly and daily global rainfall. Now use is made of the Version 1.0 bias corrected and gauge‐satellite blended precipitation product;
- FEWS‐PET: new routines for import of the daily (and the monthly) PET after 30 March 2014, as the new PET products do not require a byte swap anymore;
- Added meta data and legend to the MPE and RFS visualization (under Web Mapping Services).

# ISOD Toolbox 1.3

Some new resources have been added to this release. To assure proper operation, all internet links have been checked and modified if the URL’s or the products have changed.
## Changes
A number of additional routines have been added:
        MOD16 ET and PET products
        Soil Water Index from the Copernicus Global Land Service
        Geotif import for Landsat-8 images
        retrieval of online maps from Google and Virtual Earth.
The TAMSAT climatology has also been modified to represent the 30 years climatology currently provided.

# ISOD Toolbox 1.2

The ISOD toolbox XML version 1.2 menu structure has been modified to reflect changes due to the reprocessing of the CMORPH and TRMM rainfall data. In addition, some new resources have been added. All internet links have been checked and modified when these have changed to assure proper operation.
## Changes

The import routines of the CMORPH and TRMM 3B42 have been adapted to incorporate the changes due to reprocessing of the rainfall estimates. The TRMM extraction routine uses a small Java based utility; this requires installation of JAVA RTE.
Additional routines display Julian Day tables for normal and leap years, 3 and 6 hourly precipitation estimates from the GWADI server, GLDAS‐Noah model data (28 parameters) for 3 hour intervals on a daily basis and online rolling archive of AMESD‐SADC products (these routines have been developed by Masego Rachel Nkepu, BDMS‐Botswana).

# ISOD Toolbox 1.1

The ISOD Toolbox 1.1 menu structure has been modified substantially to accommodate a number of new data retrieval – import routines. The Web Mapping Services now focus on retrieval of data sets that are not imported into an ILWIS data format. The data is visualized using IrfanView of Panoply. All other routines extract multi‐temporal data, which is subsequently transformed into an ILWIS data format for further analysis. In addition, all routines first run a check to see if the data is available from the archives. If this is not the case, the user is informed about the missing data and can abort the import procedure. The Installation and User Guide has also been updated to reflect the changes incorporated.
## Changes

In the XML version 1.1 of the ISOD toolbox various changes have been implemented. The most important are:

- Menu modification: The web mapping services now retrieve the data and do not convert these into an ILWIS data format. The data is visualized using IrfanView and Panoply.
- Routine adaptation: All import routines have been checked and adapted if data sources have been modified (e.g. re‐processed) or if links to these data sources have changed.
- Bug fixing: Some bugs in import routines have been corrected.
- Routine check: All routines first check if data is downloaded before carrying out further processing. If no data can be retrieved the routine can be aborted.
- New routines: several routines have been added to retrieve the following data:
    TRMM 3B42 global daily rainfall archive
    MEaSUREs Global Vegetation Products (NDVI and Enhanced Vegetation Index) for various data integration periods, like daily, 7‐days, 15‐days and monthly time intervals
    NASA Global Ocean Data (day and night time SST and Chlorophyl‐a from MODIS Terra and Aqua)
    Daily Surface Soil Moisture from TRMM‐TMI (day and night time overpasses) from the Global Land Data Assimilation System
    Data visualization: visualization of data from the ECMWF, using Panoply, and NOAA‐CPC SST and SST anomaly animations
