#Python installation on debian

1. download source file

> https://www.python.org/ftp/python/3.7.0/Python-3.7.0.tar.xz

2. install dependencies

> apt install libffi-dev            #否则将会提示No module named‘_ctypes’

3. configure&make&make install  

 > ./configure --prefix=/usr/local/python3.6/ --enable-optimizations
 
 -   _hello_