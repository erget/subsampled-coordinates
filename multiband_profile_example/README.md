This example uses the [Multiband Profile](https://github.com/Unidata/EC-netCDF-CF/blob/master/swath/swath.adoc#multiband-profile) type from the CF Swath [proposal](https://github.com/Unidata/EC-netCDF-CF/blob/master/swath/swath.adoc). This swath type was selected because it can have all three types of coordinates: dimension, auxiliary, and subsampled.

The data variable (field construct) is `swath_data`. Its coordinates are:
* `pres` and `band` as dimension coordinates
* `time` as a 2D auxiliary coordinate (listed in `coordinates` attribute)
* `lat` and `lon` as subsampled coordinates (listed in `subsampled_coordinates` attribute)

Interpolation (restore) method description for computation of full resolution coordinates is in the `restore` variable.
