# pyiec61850
Server and Client of PyIEC61850 based on mz-automation

# A.	Requirements
a.	Python 3.8.10
1. Install [python-launcher](https://github.com/chanelcolgate/publishing-python-package/issues/4)
2. Install [asdf](https://github.com/chanelcolgate/publishing-python-package/issues/3)
3. sudo apt-get install python3-dev
sudo apt-get install liblzma-dev
sudo apt-get install libsqlite3-dev
sudo apt-get install libreadline-dev
sudo apt-get install -y make build-essential libssl-dev zlib1g-dev libbz2-dev \
libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev libncursesw5-dev \
xz-utils tk-dev libffi-dev liblzma-dev python-openssl
4. asdf install python 3.8.10

b.	CMake 3.7.2 or higher
1. sudo apt-get install g++
sudo apt-get install gcc
sudo apt-get install libssl-dev
2. wget wget https://github.com/Kitware/CMake/releases/download/v3.20.0/cmake-3.20.0.tar.gz
3. tar -zxvf cmake-3.20.0.tar.gz
4. cd cmake-3.20.0
5. export CC=<path_of_gcc/gcc-version>
export CXX=<path_of_g++/g++-version>
6. ./bootstrap && make && sudo make install

c.	SWIG 4.0.0 or higher
1. wget http://prdownloads.sourceforge.net/swig/swig-4.0.0.tar.gz
2. tar xzf swig-4.0.0.tar.gz
3. cd swig-4.0.0
4. ./configure
5. make
6. sudo make install

# B.	Installation
1.	cd ~
2.	sudo apt update && upgrade
3.	git clone https://github.com/keyvdir/pyiec61850.git
4.	cd pyiec61850
5.	git clone https://github.com/mz-automation/libiec61850.git
6.	wget https://github.com/Mbed-TLS/mbedtls/archive/refs/tags/v2.28.4.tar.gz
7.	tar -zxvf v2.28.4.tar.gz
8.	mv mbedtls-2.28.4/ libiec61850/third_party/mbedtls/mbedtls-2.28.4
9.	cd libiec61850
10.	py --list
11.	cmake -DBUILD_PYTHON_BINDINGS=ON -DPYTHON_EXECUTABLE=/home/mind_support/.asdf/shims/python3.8 .
12.	make WITH_MBEDTLS=1
13.	cd ..
14.	python3 server.py and python3 client.py (different terminal window)

![Server example](server.PNG)
![Client example](client.PNG)

# C.	IEC 61850 Information Model
![IEC 61850 Information Model](data.png)

# D.	Write and Read Data
Data type for write, read, and other complete functions can be found in “libiec61850/pyiec61850/iec61850.py”. Please refer to the original website of IEC61850 for further information of the data types. https://libiec61850.com/api/modules.html
