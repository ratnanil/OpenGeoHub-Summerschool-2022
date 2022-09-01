
	
tim_salabim
9:53 AM

> Dear @all, I've created a few documents for the "Visualizing cloud-optimized (large) datasets in R" workshop this afternoon that are (obviously) hosted in the cloud :slightly_smiling_face:

> Visualising cloud optimised raster data: https://cn-raster-data-vis.s3.eu-central-1.amazonaws.com/cn-raster-data-vis.html
Visualising cloud optimised vector data: https://cn-vector-data-vis.s3.eu-central-1.amazonaws.com/cn-vector-data-vis.html
Creating cloud optimised data: https://cn-data-creation.s3.eu-central-1.amazonaws.com/cloud_optimised_data.html
In the last one, you fill find instructions on how to install all the software that is needed to create cloud native data. Given that this data is hosted online in an AWS S3 bucket, this part of the tutorial is not reproducible, because I would need to give public edit access permission to all the buckets, which is generally not a good idea. All data sets can be read publicly, though. So, the visualisation parts of the turorial should just work for everyone. If you are on a windows machine, you may have problems installing all the necessary software (at least I wasn't able to). So, if anyone manages to get them installed properly, I'd be interested to know what steps are needed. All linux users should have no problems installing things, as long as you have python and git installed on your machines.

> Regarding R packages, you will need {leaflet} and the latest development version of {leafem} which you can install with remotes::install_github("r-spatial/leafem"). I also use {paws} to get a list of all the objects that are hosted in the remote buckets. 

@fdetsch will be there to help during the tutorial if people have problems installing things.

Looking forward to seeing you all later! :slightly_smiling_face:


	
leal.parente
2:16 PM
> To produce our COG files at OpenGeoHub we are using the follow command, which basically consider a tile size of 1024 pixels and the a higher compression level (9) for DEFLATE:

```sh
gdal_translate --config GDAL_CACHEMAX 2048 -co BLOCKSIZE=1024 -co BIGTIFF=YES -co COMPRESS=DEFLATE -co NUM_THREADS=6 -co LEVEL=9 -of COG
```
