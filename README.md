# CCID free software driver installer:

* Zwilla for MTW @ Travis-
[![Build Status](https://travis-ci.org/Zwilla/osx-ccid-installer.svg?branch=master)](https://travis-ci.org/Zwilla/osx-ccid-installer)

## Build Status on Libusb

* travis-ci.org/libusb
  [![Build Status](https://travis-ci.org/libusb/libusb.svg?branch=master)](https://travis-ci.org/libusb/libusb)
* LudovicRousseau/libusb
  [![Build status](https://ci.appveyor.com/api/projects/status/xvrfam94jii4a6lw?svg=true)](https://ci.appveyor.com/project/LudovicRousseau/libusb)
* scan.coverity.com/projects
  [![Coverity Scan Build Status](https://scan.coverity.com/projects/2180/badge.svg)](https://scan.coverity.com/projects/libusb-libusb)

### Easy-to-use (graphical) installer for OSX 10.11 & 10.12

* To **download a pre-built installer, see
  [releases](https://github.com/zwilla/osx-ccid-installer/releases)**
* To get help:
  [file an issue](https://github.com/zwilla/osx-ccid-installer/issues/new)
* To build yourself (requires XCode plus `libtool`, `autoconf`,
  `automake` and `pkg-config` from Homebrew/MacPorts/Fink)
  * OSX-Terminal: ``brew libtool autoconf automake pkg-config``

```
  git clone --recursive https://github.com/martinpaljak/osx-ccid-installer
  make -C osx-ccid-installer
```

#### Development

* To build a signed release:

```
  make SIGNER="XXX" 
  # OR 
  make SIGNER="Developer ID Application: XXX"
```
* Zwilla cut of the money making Apple Cert, now you can sign with your own CA! See changes on MAKEFILE
    * If you want to sign with an apple ID: make SIGNER="Developer ID Application: XXX"
* where `XXX` is the personal part of a
  [Developer ID](https://developer.apple.com/developer-id/) certificate
  common name, such as `Martin Paljak` or `Martin Paljak (9ME8T34MPV)`
  * You can list your ID-s with `security find-identity -v -p
    codesigning`


#### Trusted Release

We switched from money making apple developer id to our own
MyTokenWallet CA to sign the dmg file our CodeSigning Cert you will find
here: https://mytokenwallet.com/MTW_CA.cert

#### Because of
[OSX bugs](http://ludovicrousseau.blogspot.com/2016/04/os-x-el-capitan-and-ccid-driver-upgrades.html)
and
[features](https://en.wikipedia.org/wiki/System_Integrity_Protection);
built from the excellent
[CCID free software driver](http://pcsclite.alioth.debian.org/ccid.html)
[sources](https://github.com/LudovicRousseau/CCID), the
["official unofficial"](https://github.com/LudovicRousseau/CCID/issues/17#issuecomment-216467582):
