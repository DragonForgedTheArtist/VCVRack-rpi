# VCVRack-rpi
VCV Rack build instructions and patch for Raspberry Pi

## Install Dependencies
First, you will need to install dependencies.
    
    sudo apt-get install unzip git gdb curl cmake libx11-dev libglu1-mesa-dev libxrandr-dev libxinerama-dev libxcursor-dev libxi-dev zlib1g-dev libasound2-dev libgtk2.0-dev libgtk-3-dev libjack-jackd2-dev jq zstd libpulse-dev pkg-config markdown autoge

## Build instructions
clone this repo

    git clone https://github.com/DragonForgedTheArtist/VCVRack-rpi.git

clone the VCV Rack repo and apply the patch

    git clone https://github.com/VCVRack/Rack.git
    cd Rack
    patch -p1 <../VCVRack-rpi/Rack-arm.patch

Follow the standard build instructions, including building the fundamental plugin.

    git submodule update --init --recursiveGit
    make dep
    make
    make run

If all goes smooth with Make Run, fix the missing module problem it just complained about.

    cd plugins
    git clone https://github.com/VCVRack/Fundamental.git
    cd Fundamental
Git submodule update --init --recursive
    make dep
    make
    cd ../..
    make run

Create a new file to correct the missing modules in the autosave caused by the error above.  If all goes well, then

    make dist

