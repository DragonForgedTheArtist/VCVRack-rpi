# The Patches

Below is a description of what each patch does and how to apply it.

## Rack-arm.patch
This is the main patch that allows VCV Rack to compile on arm linux without errors.
- libsamplerate-0.1.9 failes to detect arm linux.  this is fixed in libsamplerate-0.2.1.  The patch upgrades the libsamplerate version in deps/Makefile
- adds archetecture detectio for arm linux to arch.mk
- linux builds are hardcoded for x86_64 in compile.mk.  The patch uses the added archetecture detection to fix this. 

        #From the top level of the rack source tree
        patch -p1 <../VCVRack-rpi/patches/Rack-arm.patch

## CausalSystems-libsamplerate.patch
Some plugins are linked against libsamplerate-0.1.9 which has archetecture detection issues on arm linux.  This patch upgrade libsamplerate to version 0.2.1 for Causal Systems

    patch -p1 < ../../../VCVRack-rpi/patches/CausalSystems-libsamplerate.patch

## FehlerFabrik-libsamplerate.patch
Some plugins are linked against libsamplerate-0.1.9 which has archetecture detection issues on arm linux.  This patch upgrade libsamplerate to version 0.2.1 for Fehler Fabrik

    patch -p1 < ../../../VCVRack-rpi/patches/FehlerFabrik-libsamplerate.patch

## Recorder-ffmpeg-mirrir.patch
In some cases, the official ffmpeg repository is unaccessable for cloning. This patch replaces the source url for the ffmpeg submodule with the official github mirror

    # From the top level of the VCV-Recorder plugin source
    patch -p1 <../../../VCVRack-rpi/patches/Recorder-ffmpeg-mirror.patch

## tcRackModules_typo_fix.patch
There is a small typo in ArpGen.cpp.  This patch fixes a case sensitivity issue.

    # From the top level of the tcRackModules plugin source
    patch -p1 <../../../VCVRack-rpi/patches/tcRackModules_typo_fix.patch

