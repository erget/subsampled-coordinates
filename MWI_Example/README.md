Encode the subsampling of EPS-SG MWI L1B product

MWI is a sensor that will fly on board the EPS-SG satellites.
It is a conically scanning instrument.

In the L1B files, the swath data (brightness temperatures) will be
presented as 2D arrays with coordinates (nscanlines,nscanpos).

The geolocation data will be subsampled by scanpos (e.g. 1 every 8 scanpos)
but not by scanlines. This is thus a 1D interpolation of just the scanpos.
The interpolation is linear between the tiepoints, but should be performed
on the cartesian X,Y,Z coordinates, not directly on lat/lon (to avoid singularities).

