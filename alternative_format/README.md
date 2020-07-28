Rationale
=========

The subsampling/compaction mechanism should have minimal effect on the data
variables that use subsampled/compacted variables as coordinates.

All the information required to restore the full content of a
subsampled/compacted variable should be attached to this variable, either
directly (attributes) or by transitivity (other variables pointed by
attributes).

Using subsampled/compacted coordinates
--------------------------------------
As subsampled/compacted variables are not supported by the standard yet, they
cannot be included in the "coordinates" attribute of variables (backward
compatibility). Another attribute, "subsampled\_coordinates" shall be used for
these subsampled/compacted coordinates variables.

Mapping subsampled and full dimensions
--------------------------------------
The relation between subsampled and full dimensions is expressed through
indices variables. The index values contained in these variables refer to the
full dimension indicated in the "subsamples\_dimension" attribute.

Methods for reconstructing full variables
-----------------------------------------
A container variable (no data, only attributes) is used to describe methods to
reconstruct full data from subsampled/compacted variables.

These container variables have one mandatory attribute: "standard\_name".
The value of this attribute is a string that identifies the reconstruction
method. The CF conventions must provide a detailed description of the algorithm
attached to each available method.

If the method accepts parameters, they must be provided with the
"formula\_terms".

See Annex D for similar examples already in CF conventions:
http://cfconventions.org/Data/cf-conventions/cf-conventions-1.7/build/apd.html

Reconstructing fuil variables
-----------------------------
Subsampled/compacted variables need two attributes to provides the means for
reconstructing their full content:
 * "restore\_method": this attribute must point to the container variable that
                     describes the reconstruction method.
 * "restore\_indices": this attribute must associate each dimension of the
                      subsampled variable with an indices variable.

In case additional parameters must be passed to the reconstruction method, they
should be provided with the "restore\_terms" attribute.

Extra case: shared subsampled coordinates at multiple resolutions
-----------------------------------------------------------------
Subsampled/compacted variables as they are described above can only be used as
coordinates for data variables that share the same full dimensions.

In case subsampled/compacted coordinates should be shared by data variables
with different full coordinates, i.e. if reconstruction parameters are specific
to the data variables, then the data variable should have an additional
attribute, "restore\_indices\_override", to define its own mapping between
subsampled coordinates and indices variables.

See the m\_radiance variable in  viirs\_m\_and\_i\_band\_example.cdl
