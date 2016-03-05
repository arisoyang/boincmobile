# Compiling BOINC on a Ubuntu platform #



### Building on a Ubuntu Cortex-A8 ###

```
#!/bin/bash

sudo apt-get install autoconf m4 openssl libcurl4-openssl-dev libtool subversion libfftw3-dev

svn co http://boinc.berkeley.edu/svn/trunk/boinc 
cd boinc/
./_autosetup
./configure --disable-server CXXFLAGS="-O3 -mtune=cortex-a8 -mfpu=neon" CFLAGS="-O3 -mtune=cortex-a8 -mfpu=neon"
make

svn checkout https://setisvn.ssl.berkeley.edu/svn/seti_boinc
cd ../seti_boinc
./_autosetup
./configure --disable-server CXXFLAGS="-O3 -mtune=cortex-a8 -mfpu=neon" CFLAGS="-O3 -mtune=cortex-a8 -mfpu=neon"
make
```

### Building on a Ubuntu Cortex-A9 ###

```
#!/bin/bash

sudo apt-get install autoconf m4 openssl libcurl4-openssl-dev libtool subversion libfftw3-dev

svn co http://boinc.berkeley.edu/svn/trunk/boinc 
cd boinc/
./_autosetup
./configure --disable-server CXXFLAGS="-O3 -mtune=cortex-a9 -mfpu=neon" CFLAGS="-O3 -mtune=cortex-a9 -mfpu=neon"
make

svn checkout https://setisvn.ssl.berkeley.edu/svn/seti_boinc
cd ../seti_boinc
./_autosetup
./configure --disable-server CXXFLAGS="-O3 -mtune=cortex-a9 -mfpu=neon" CFLAGS="-O3 -mtune=cortex-a9 -mfpu=neon"
make
```

### Building on a Ubuntu Atom ###

```
#!/bin/bash

sudo apt-get install autoconf m4 openssl libcurl4-openssl-dev libtool subversion libfftw3-dev

svn co http://boinc.berkeley.edu/svn/trunk/boinc 
cd boinc/
./_autosetup
./configure --disable-server CXXFLAGS="-O3 -mtune=atom" CFLAGS="-O3 -mtune=atom"
make

svn checkout https://setisvn.ssl.berkeley.edu/svn/seti_boinc
cd ../seti_boinc
./_autosetup
./configure --disable-server CXXFLAGS="-O3 -mtune=atom" CFLAGS="-O3 -mtune=atom"
make
```

### Building on a Ubuntu Core i3 ###

```
#!/bin/bash

sudo apt-get install autoconf m4 openssl libcurl4-openssl-dev libtool subversion libfftw3-dev

svn co http://boinc.berkeley.edu/svn/trunk/boinc 
cd boinc/
./_autosetup
./configure --disable-server CXXFLAGS="-O3 -mtune=core2" CFLAGS="-O3 -mtune=core2"
make

svn checkout https://setisvn.ssl.berkeley.edu/svn/seti_boinc
cd ../seti_boinc
./_autosetup
./configure --disable-server CXXFLAGS="-O3 -mtune=core2" CFLAGS="-O3 -mtune=core2"
make
```


### Using Super Optimized Version of FFTW ###
Note: I didn't see much performance difference with this versus the debian package and thus ended up using the .deb version
Project Link: http://code.google.com/p/fftw-neon/
```
wget http://www.fftw.org/fftw-3.2.2.tar.gz 
tar xvzf fftw-3.2.2.tar.gz
cd ../fftw-3.2.2/
./configure --prefix=/usr --enable-single --enable-shared --with-pic CFLAGS="-O3 -pipe -mcpu=cortex-a9 -mfpu=neon -mfloat-abi=softfp"
make
sudo make install

cd ../fftw-3.2.2/
wget http://code.google.com/p/fftw-neon/downloads/detail?name=fftw-3.2.2-neon-1.diff
patch -p1 < fftw-3.2.2-neon-1.diff
./configure --prefix=/usr --enable-single --enable-shared --with-pic CFLAGS="-O3 -pipe -mcpu=cortex-a9 -mfpu=neon -mfloat-abi=softfp"
make
sudo make install
```