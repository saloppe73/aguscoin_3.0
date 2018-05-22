### Linux (Debian/Ubuntu/Mint)

- You will need the following packages: boost (1.55 or higher), rocksdb, cmake, git, gcc (4.9 or higher), g++ (4.9 or higher), make, and python. Most of these should already be installed on your system.
- For example on ubuntu: 
```
sudo apt-get install build-essential python-dev gcc g++ git cmake libboost-all-dev librocksdb-dev
```
- If you are using ubuntu and your version of ubuntu doesn't have librocksdb-dev, you can get it from a ppa instead:
```
sudo add-apt-repository ppa:ethcore/ethcore -y
sudo apt-get update
sudo apt-get install librocksdb-dev
```
##### Building
```
git clone https://github.com/saloppe73/aguscoin_3.0.git
cd aguscoin_3.0
mkdir build && cd build && cmake .. && make
```

The binaries will be in `/build/src` after compilation is complete.

##### Running Daemon

```
./aguscoind
```

##### Running Wallet
```
./agus-wallet
```

---------------------------------------------------------------------------

### Apple

##### Prerequisites

- Install [cmake](https://cmake.org/). See [here](https://stackoverflow.com/questions/23849962/cmake-installer-for-mac-fails-to-create-usr-bin-symlinks) if you are unable call `cmake` from the terminal after installing.
- Install the [boost](http://www.boost.org/) libraries. Either compile boost manually or run `brew install boost`.
- Install XCode and Developer Tools.

##### Building
```
git clone https://github.com/saloppe73/aguscoin_3.0.git
cd aguscoin_3.0
mkdir build && cd build && cmake .. && make
```

The binaries will be in `/build/release/src` after compilation is complete.

---------------------------------------------------------------------------

### Windows 10

##### Prerequisites
- Install [Visual Studio 2017 Community Edition](https://www.visualstudio.com/thank-you-downloading-visual-studio/?sku=Community&rel=15&page=inlineinstall)
- When installing Visual Studio, it is **required** that you install **Desktop development with C++** and the **VC++ v140 toolchain** when selecting features. The option to install the v140 toolchain can be found by expanding the "Desktop development with C++" node on the right. You will need this for the project to build correctly.
- Install [Boost 1.59.0](https://sourceforge.net/projects/boost/files/boost-binaries/1.59.0/), ensuring you download the installer for MSVC 14.

##### Building

- From the start menu, open 'x64 Native Tools Command Prompt for vs2017'.
```
cd <your_aguscoin_directory>
mkdir build
cd build
```

- Set the PATH variable for cmake: ie.
```
set PATH="C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\Common7\IDE\CommonExtensions\Microsoft\CMake\CMake\bin";%PATH%
```
- run cmake
```
cmake -G "Visual Studio 14 Win64" .. -DBOOST_ROOT=C:/local/boost_1_59_0
```
- finally build it
```
MSBuild ByteCoin.sln /p:Configuration=Release /m
```

You will find all your binaries in the '..\build\src\Release' directory.

#### cheers goes to bytecoin && monero && turtle
