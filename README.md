# VCVRack-rpi
VCV Rack build instructions and patch for Raspberry Pi

## Install Dependancies
First you will need to install dependancies 
    
    sudo apt install unzip git gdb curl cmake libx11-dev libglu1-mesa-dev libxrandr-dev libxinerama-dev libxcursor-dev libxi-dev zlib1g-dev libasound2-dev libgtk2.0-dev libgtk-3-dev libjack-jackd2-dev jq zstd libpulse-dev pkg-config markdown autoge

## Build instructions
clone this repo

    git clone https://github.com/DragonForgedTheArtist/VCVRack-rpi.git

clone the VCV Rack repo and apply the patch

    git clone https://github.com/VCVRack/Rack.git
    cd Rack
    patch -p1 <../VCVRack-rpi/Rack-arm.patch

Follow the standard build instructions including building the fundamental plugin.

    git submodule update --init --recursive
    make dep
    make
    make run

If all goes smooth with make run, fix the missing modules problem it just complained about.

    cd plugins
    git clone https://github.com/VCVRack/Fundamental.git
    cd Fundamental
    git submodule update --init --recursive
    make dep
    make
    cd ../..
    make dist

