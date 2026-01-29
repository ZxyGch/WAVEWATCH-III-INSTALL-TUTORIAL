If you find this tutorial useful, please give it a star ⭐

I have another tool developed for WAVEWATCH III users: https://github.com/ZxyGch/WW3Tool

# Ubuntu

```swift
sudo apt install gcc  g++  gfortran  make mpich libopenmpi-dev zlib1g-dev cmake git libhdf5-dev libnetcdf-dev libnetcdff-dev
```

```sh
git clone https://github.com/NOAA-EMC/WW3.git

cd WW3

mkdir build && cd build

cmake .. \
  -DSWITCH=NCEP_st4 \
  -DCMAKE_INSTALL_PREFIX=install 
  
make -j

sudo make install  
```

Then perform regression test

```sh
cd ../regtests && bin/run_cmake_test ../model mww3_test_01    
```

like this,  install WAVEWATCH III success 🎉

```swift
-rw-r--r--   1 zxy  staff     6498  1 29 11:42 ww3.68060606.hs
-rw-r--r--   1 zxy  staff     6498  1 29 11:42 ww3.68060606.ice
-rw-r--r--   1 zxy  staff     6498  1 29 11:42 ww3.68060607.hs
-rw-r--r--   1 zxy  staff     6498  1 29 11:42 ww3.68060607.ice
-rw-r--r--   1 zxy  staff     6498  1 29 11:42 ww3.68060608.hs
-rw-r--r--   1 zxy  staff     6498  1 29 11:42 ww3.68060608.ice
-rw-r--r--   1 zxy  staff     6498  1 29 11:42 ww3.68060609.hs
-rw-r--r--   1 zxy  staff     6498  1 29 11:42 ww3.68060609.ice
-rw-r--r--   1 zxy  staff     6498  1 29 11:42 ww3.68060610.hs
-rw-r--r--   1 zxy  staff     6498  1 29 11:42 ww3.68060610.ice
-rw-r--r--   1 zxy  staff     6498  1 29 11:42 ww3.68060611.hs
-rw-r--r--   1 zxy  staff     6498  1 29 11:42 ww3.68060611.ice
-rw-r--r--   1 zxy  staff     6498  1 29 11:42 ww3.68060612.hs
-rw-r--r--   1 zxy  staff     6498  1 29 11:42 ww3.68060612.ice
 
 
                    ==================================   
                  ======>  END OF WAVEWATCH III  <====== 
                    ================================== 
```

In the  WW3/build/bin, we can find 

```swift
gx_outf    ww3_bound  ww3_grid   ww3_ounf   ww3_outp   ww3_shel   ww3_trck
gx_outp    ww3_gint   ww3_gspl   ww3_ounp   ww3_prep   ww3_strt   ww3_trnc
ww3_bounc  ww3_grib   ww3_multi  ww3_outf   ww3_prnc   ww3_systrk ww3_uprstr
```







# MacOS

## Install brew

```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```



## Install Others

```swift
brew install gcc open-mpi zlib hdf5 netcdf-c netcdf-fortran
```

Check the install is successful

```swift
gcc --version
gfortran --version
mpicc --version
mpif90 --version
mpirun --version
nc-config --all
nf-config --all
```



## Install  WAVEWATCH III 

```sh
git clone https://github.com/NOAA-EMC/WW3.git

cd WW3

mkdir build && cd build

cmake .. \
  -DSWITCH=NCEP_st4 \
  -DCMAKE_INSTALL_PREFIX=install 
  
make 

make install  
```

Then perform regression test

```sh
cd ../regtests && bin/run_cmake_test ../model mww3_test_01    
```

like this,  install WAVEWATCH III Success 🎉

```swift
-rw-r--r--   1 zxy  staff     6498  1 29 11:42 ww3.68060606.hs
-rw-r--r--   1 zxy  staff     6498  1 29 11:42 ww3.68060606.ice
-rw-r--r--   1 zxy  staff     6498  1 29 11:42 ww3.68060607.hs
-rw-r--r--   1 zxy  staff     6498  1 29 11:42 ww3.68060607.ice
-rw-r--r--   1 zxy  staff     6498  1 29 11:42 ww3.68060608.hs
-rw-r--r--   1 zxy  staff     6498  1 29 11:42 ww3.68060608.ice
-rw-r--r--   1 zxy  staff     6498  1 29 11:42 ww3.68060609.hs
-rw-r--r--   1 zxy  staff     6498  1 29 11:42 ww3.68060609.ice
-rw-r--r--   1 zxy  staff     6498  1 29 11:42 ww3.68060610.hs
-rw-r--r--   1 zxy  staff     6498  1 29 11:42 ww3.68060610.ice
-rw-r--r--   1 zxy  staff     6498  1 29 11:42 ww3.68060611.hs
-rw-r--r--   1 zxy  staff     6498  1 29 11:42 ww3.68060611.ice
-rw-r--r--   1 zxy  staff     6498  1 29 11:42 ww3.68060612.hs
-rw-r--r--   1 zxy  staff     6498  1 29 11:42 ww3.68060612.ice
 
 
                    ==================================   
                  ======>  END OF WAVEWATCH III  <====== 
                    ================================== 
```

In the  WW3/build/bin, we can find 

```swift
gx_outf    ww3_bound  ww3_grid   ww3_ounf   ww3_outp   ww3_shel   ww3_trck
gx_outp    ww3_gint   ww3_gspl   ww3_ounp   ww3_prep   ww3_strt   ww3_trnc
ww3_bounc  ww3_grib   ww3_multi  ww3_outf   ww3_prnc   ww3_systrk ww3_uprstr
```


