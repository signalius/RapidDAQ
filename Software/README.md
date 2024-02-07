This repository contains host software (Linux/Windows) for RapidDAQ.

## How to build the host software on Linux:

### Prerequisites for Linux (Debian/Ubuntu):
`sudo apt-get install build-essential cmake libusb-1.0-0-dev pkg-config`

### Build host software on Linux:
```
mkdir host/build
cd host/build
cmake ..
make
sudo make install
sudo ldconfig
```

By default this will attempt to install an udev rule to `/etc/udev/rules.d` to
provide the `usb` or `plugdev` group access to RapidDAQ. If your setup requires
the udev rule to be installed elsewhere you can modify the path with
`-DUDEV_RULES_PATH=/path/to/udev`.

## Clean CMake temporary files/dirs:
```
cd host/build
rm -rf *
```

## How to build host software on Windows:
### Prerequisites for Cygwin, MinGW, or Visual Studio:

* cmake-2.8.12.1 or later from http://www.cmake.org/cmake/resources/software.html
* libusbx-1.0.18 or later from http://sourceforge.net/projects/libusbx/files/latest/download?source=files
* fftw-3.3.5 or later from http://www.fftw.org/install/windows.html
* Install Windows driver for RapidDAQ hardware or use Zadig see http://sourceforge.net/projects/libwdi/files/zadig
  - If you want to use Zadig select RapidDAQ USB device and just install/replace it with WinUSB driver.

### For Cygwin:
```
mkdir host/build
cd host/build
cmake ../ -G "Unix Makefiles" -DCMAKE_LEGACY_CYGWIN_WIN32=1 -DLIBUSB_INCLUDE_DIR=/usr/local/include/libusb-1.0/
make
make install
```

### For MinGW:
```
mkdir host/build
cd host/build
cmake ../ -G "MSYS Makefiles" -DLIBUSB_INCLUDE_DIR=/usr/local/include/libusb-1.0/
make
make install
```

## How to build the host software on macOS:

### Install dependencies

Homebrew: `brew install cmake libusb pkg-config`

### Build it
```sh
mkdir host/build
cd host/build
cmake ..
make
sudo make install
sudo update_dyld_shared_cache # equivalent to ldconfig in linux
```

## Credits

Author: Tomasz Orlowski
This work is based on libhackrf 


