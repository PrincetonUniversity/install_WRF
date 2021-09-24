# Installing latest version 3
- download source code 
```
wget https://github.com/wrf-model/WRF/archive/refs/tags/V3.9.1.1.tar.gz
```
- prepare the sources
```
tar xf V3.9.1.1.tar.gz
cd WRF-3.9.1.1
```
- copy file `intel-mpi-env.sh` below and execute it to set up the environment
```
chmod u+x intel-mpi-env.sh
source intel-mpi-env.sh
```
- modify the `configure` file with this sed command:
```
sed -i 's,lib/libnetcdf,lib64/libnetcdf,g' configure
```
```
./configure
# choose 15 or whatever you need
# choose default
```
- compile
```
export J="-4"
./compile em_real
```

# Installing latest version 4
The only differnce compared to v 3 is the link
```
wget https://github.com/wrf-model/WRF/archive/refs/tags/v4.3.tar.gz
```

# User guides
- User guide for v 3:
  https://www2.mmm.ucar.edu/wrf/users/docs/user_guide_V3/
- User guide for v 4:
  https://www2.mmm.ucar.edu/wrf/users/docs/user_guide_v4/
  
 # Note on SLURM script when running the code
 To set up the environment when you execute the code, you need to add:
 ```
 source intel-mpi-env.sh
 ```
 before your `srun` line.
 
