🥳 If you find this tutorial useful, please give me a star ⭐ 🥳

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
ROOT=$(cd .. && pwd)
CASE=$ROOT/regtests/ww3_tp1.1
BIN=$ROOT/build/bin
WORK=$CASE/work_install_smoke

mkdir -p "$WORK" \
&& rsync -a --ignore-existing "$CASE/input/" "$WORK/" \
&& cd "$WORK" \
&& for exe in ww3_grid ww3_strt ww3_shel; do
     "$BIN/$exe"
   done 
```

like this,  install WAVEWATCH III success 🎉

```swift
  WAVEWATCH III calculating for 1968/06/06 20:00:00 UTC at 14:30:51
  WAVEWATCH III calculating for 1968/06/06 21:00:00 UTC at 14:30:51
  WAVEWATCH III calculating for 1968/06/06 22:00:00 UTC at 14:30:51
  WAVEWATCH III calculating for 1968/06/06 23:00:00 UTC at 14:30:51
  WAVEWATCH III calculating for 1968/06/07 00:00:00 UTC at 14:30:51
  WAVEWATCH III reached the end of a computation loop at 14:30:51

  Initialization time :      0.08 s
  Elapsed time        :      0.08 s

  End of program 
 ====================================
         WAVEWATCH III Program shell 
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
ROOT=$(cd .. && pwd)
CASE=$ROOT/regtests/ww3_tp1.1
BIN=$ROOT/build/bin
WORK=$CASE/work_install_smoke

mkdir -p "$WORK" \
&& rsync -a --ignore-existing "$CASE/input/" "$WORK/" \
&& cd "$WORK" \
&& for exe in ww3_grid ww3_strt ww3_shel; do
     "$BIN/$exe"
   done 
```

like this,  install WAVEWATCH III Success 🎉

```swift
  WAVEWATCH III calculating for 1968/06/06 20:00:00 UTC at 14:30:51
  WAVEWATCH III calculating for 1968/06/06 21:00:00 UTC at 14:30:51
  WAVEWATCH III calculating for 1968/06/06 22:00:00 UTC at 14:30:51
  WAVEWATCH III calculating for 1968/06/06 23:00:00 UTC at 14:30:51
  WAVEWATCH III calculating for 1968/06/07 00:00:00 UTC at 14:30:51
  WAVEWATCH III reached the end of a computation loop at 14:30:51

  Initialization time :      0.08 s
  Elapsed time        :      0.08 s

  End of program 
 ====================================
         WAVEWATCH III Program shell 
```

In the  WW3/build/bin, we can find 

```swift
gx_outf    ww3_bound  ww3_grid   ww3_ounf   ww3_outp   ww3_shel   ww3_trck
gx_outp    ww3_gint   ww3_gspl   ww3_ounp   ww3_prep   ww3_strt   ww3_trnc
ww3_bounc  ww3_grib   ww3_multi  ww3_outf   ww3_prnc   ww3_systrk ww3_uprstr
```


