### Target board </br>
https://www.xilinx.com/support/university/boards-portfolio/xup-boards/DigilentZYBO.html#resources

RM</br>
https://www.xilinx.com/content/dam/xilinx/support/documentation/university/XUP%20Boards/XUPZYBO/documentation/ZYBO_RM_B_V6.pdf

### 1. Installing Petalinux</br>
Download petalinux installer at Xillinx webpage. Version v2017.4

RM</br>
https://www.xilinx.com/support/documentation/sw_manuals/xilinx2017_4/ug1144-petalinux-tools-reference-guide.pdf

Follow Digilent bsp github</br>
https://github.com/Digilent/Petalinux-Zybo/tree/master

While installing petalinux, Error would occur because Ubuntu 20.04 does not su>pport python package.
>dpkg-query: package 'python' is not installed and no information is available Use dpkg --info (= dpkg-deb --info) to examine archive files ERROR: You have tools don't meet the version requirements: -Detected python version is less than the expected 2.7.3

Solution</br>
https://stackoverflow.com/questions/62980416/python-error-when-installing-xilinx-petalinux-on-ubuntu-20-04

1. Install python2
```
sudo apt install python2
```
2. append /var/lib/dpkg/status
```
Package: python
Status: install ok installed
Maintainer: Fake Entry <fake@example.com>
Architecture: all
Version: 2.7.17
Description: fake package for petalinux
```

### 2. Building Petalinux</br>

While `petalinux-build`, locale error would occur.
>You system needs to support the en_US.UTF-8 locale.

`sudo dpkg-reconfigure locales ` to set system default 

## Error not resloved
output of my system `locale`

```
LANG=en_US.UTF-8
LANGUAGE=
LC_CTYPE="en_US.UTF-8"
LC_NUMERIC="en_US.UTF-8"
LC_TIME="en_US.UTF-8"
LC_COLLATE="en_US.UTF-8"
LC_MONETARY="en_US.UTF-8"
LC_MESSAGES="en_US.UTF-8"
LC_PAPER="en_US.UTF-8"
LC_NAME="en_US.UTF-8"
LC_ADDRESS="en_US.UTF-8"
LC_TELEPHONE="en_US.UTF-8"
LC_MEASUREMENT="en_US.UTF-8"
LC_IDENTIFICATION="en_US.UTF-8"
LC_ALL=
```

But prints the same error.

## I should study about yocto!
