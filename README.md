# docker-arduino-toolchain

This is a docker container that builds and uses the [arduino toolchain](https://github.com/arduino/toolchain-avr) directly, without using the Arduino IDE.

# Usage

To create the image, run `docker build -t arduino .`. There is an optional `--build-arg` of `TOOLCHAIN_ARCHIVE` so that you may point to a fork or branch, it defaults to `https://github.com/arduino/toolchain-avr/archive/master.zip`.

To get the results of the build you could do something like `docker run -v /tmp/avr:/tohost arduino cp -r /objdir/bin /tohost`.

If you want to just use the binaries in the container, try `docker run arduino avr-cpp --help`. Maybe you'd like to `alias dra=docker run arduino` or similar.
