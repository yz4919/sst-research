# sst-research

Source of netCDF file: https://www.metoffice.gov.uk/hadobs/hadisst/data/download.html 

import netCDF4 as nc
import numpy as np

# Access file
file_path = '/Users/yutanzhang/Desktop/SST/HadISST_sst.nc'

# Open NetCDF
dataset = nc.Dataset(file_path, mode='r')

# Print basic file information
print("File format:", dataset.file_format)
print("Dimensions:")
for dim in dataset.dimensions.values():
    print(f"  {dim.name}: {len(dim)}")

print("\nVariables:")
for var_name, var in dataset.variables.items():
    print(f"  {var_name}: {var.dimensions} -> {var.dtype}")

# Close file
dataset.close()

File format: NETCDF3_CLASSIC
Dimensions:
  time: 1864
  latitude: 180
  longitude: 360
  nv: 2

Variables:
  time: ('time',) -> float32
  time_bnds: ('time', 'nv') -> float32
  latitude: ('latitude',) -> float32
  longitude: ('longitude',) -> float32
  sst: ('time', 'latitude', 'longitude') -> float32
