Example based on VIIRS M-Band (750 m resolution imaging) and VIIRS I-Band (375 m resolution imaging) radiance data variables.

The M-Band and I-Band radiance data variables shares the common compacted geolocation, viweing angle and time defined by the tp_interpolation and time_interpolation containers.

The shared interpolation containers references:
  - an interpolation method (interpolation_name)
  - interpolation coefficients
  - interpolation flags
  - location tie points
  - sensor direction tie points 
  - solar direction tie points

Each of the M-Band and I-Band radiance data sets has a interpolation_indices attribute referenceing an indices variable. The indices varibale provides the indices of the tie points in the uncompacted product dimensions.  The indices varibale are not shared between the M- and I bands, as these have different dimensions. 
