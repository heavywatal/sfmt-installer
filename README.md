## SFMT-class

This is an unofficial wrapper of SFMT for C++.
It can also be used as a simple installer of SFMT and dSFMT for C/C++.
SFMT is a new variant of Mersenne Twister (MT) introduced by Mutsuo Saito and Makoto Matsumoto.

http://www.math.sci.hiroshima-u.ac.jp/~m-mat/MT/SFMT/

### Installation

Download and extract [released archive](https://github.com/heavywatal/sfmt-class/releases)

```sh
% ./configure --prefix=${HOME}/local
% make
% make install
```

If you are building the latest development version from github,
you need to initiate submodules and run **autotools**
to get the SFMT source files and ``configure`` script

```sh
% git clone https://github.com/heavywatal/sfmt-class.git
% cd sfmt-class/
% git submodule update --init
% autoreconf -i
```

### Usage in C++

C++ header `sfmt.hpp` is installed in addition to the original C headers.
A wrapper class `wtl::sfmt19937` is compatible with `std::mt19937` and can be used in combination with `std::*_distribution` in `<random>`.
For convenience, a static object is initialized with `std::random_device`, and its reference is provided through an inline function `sfmt()`.
See ``example.cpp`` and try `make example`.
