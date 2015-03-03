
wiringPi README
===============

Please note that the official way to get wiringPi is via git from
git.drogon.net and not GitHub.

ie.

  git clone git://git.drogon.net/wiringPi

The version of wiringPi held on GitHub by "Gadgetoid" is used to build the
wiringPython, Ruby, Perl, etc. wrappers for these other languages. This
version may lag the official Drogon release.  Pull requests may not be
accepted to Github....

Please see

  http://wiringpi.com/

for the official documentation, etc. and the best way to submit bug reports, etc.
is by sending an email to projects@drogon.net

Compiling for emscripten
------------------------

Install emscripten tools into path (emmake and emcc) and run:

  cd wiringPi
  make emscripten

This creates a file libwiringPi-X.XX.js (where X.XX is the version number).
To use a pre-file, f.e. to set up node.js file system mapping, use:

  EMCC_ARGS="--pre-js libwiringPi-pre.js" make emscripten

Cross compiling
---------------

To compile for Raspberry Pi from your desktop computer, obtain the 
arm-linux-gnueabihf toolchain, then override the compiler:

  cd wiringPi
  CC=~/arm-linux-gnueabihf-4.8/bin/arm-linux-gnueabihf-gcc \
  AR=~/arm-linux-gnueabihf-4.8/bin/arm-linux-gnueabihf-ar \
  RANLIB=~/arm-linux-gnueabihf-4.8/bin/arm-linux-gnueabihf-ranlib \
  make

Thanks!

  -Gordon
