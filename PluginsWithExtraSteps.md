# Plugins That Require Extra Steps To Compile
The following plugins require extra steps to compile successfully.

## AlgoritmArte
AlgoritmArte doesn't default to the v2 branch so it will need to be checked out

    git clone --branch v2 https://github.com/algoritmarte/AlgoritmarteVCVPlugin.gi

Then build as normal

    cd AlgoritmarteVCVPlugin
    git submodule update --init --recursive
    make dep
    make
    make install

## CharredDesert
CharredDesert doesn't default to the 2.0 branch so it will need to be checked out

    git clone --branch v2.0 https://github.com/SVModular/CharredDesert.git

Then build as normal

    cd CharredDesert
    git submodule update --init --recursive
    make dep
    make
    make install

## Fehler Fabrik
Check out the repository as normal
    git clone https://github.com/RCameron93/FehlerFabrik.git    

Apply the patch to upgrade libsamplerate to version 0.2.1

    cd FehlerFabrik
    patch -p1 < ../../../VCVRack-rpi/patches/FehlerFabrik-libsamplerate.patch

Then build as normal

    git submodule update --init --recursive
    make dep
    make
    make install

## LifeFormModular
LifeFormModular doesn't default to the V2 branch so it will need to be checked out

    git clone --branch V2 https://github.com/TimeControlledOrganism/LifeFormModular.git
    

Then build as normal

    cd LifeFormModular
    git submodule update --init --recursive
    make dep
    make
    make install

## LSFR
LSFR doesn't default to the 2.0 branch so it will need to be checked out

    git clone --branch V2X https://github.com/alto777/LFSR.git

Then build as normal

    cd LSFR
    git submodule update --init --recursive
    make dep
    make
    make install

## OrangeLine
OrangeLine doesn't default to the 2.0 branch so it will need to be checked out

    git clone --depth 1 --branch 2.0 https://github.com/Stubs42/OrangeLine.git

Then build as normal

    cd OrangeLine
    git submodule update --init --recursive
    make dep
    make
    make install

## PS-PurrSoftware
PS-PurrSoftware doesn't default to the master-V2 branch so it will need to be checked out

    git clone --branch master-V2 https://github.com/knchaffin/Meander.git

Then build as normal

    cd Meander
    git submodule update --init --recursive
    make dep
    make
    make install

## RPJ
RPG doesn't default to the v2 branch so it will need to be checked out

    git clone --branch v2 https://github.com/kockie69/RPJ.git

Then build as normal

    cd RPJ
    git submodule update --init --recursive
    make dep
    make
    make install

## stocaudio
Check out the repository as normal
    git clone https://github.com/aptrn/stocaudio-modules.git

Apply the patch to upgrade libsamplerate to version 0.2.1

    cd stocaudio-modules
    patch -p1 --dry-run < ../../../VCVRack-rpi/patches/stocaudio-modules-libsamplerate.patch

Then build as normal

    git submodule update --init --recursive
    make dep
    make
    make install

## Tonecarver
Tonecarver doesn't default to the v2 branch so it will need to be checked out

    git clone --branch v2 https://github.com/Tonecarver/tcRackModules.git

There is a small typo in ArpGen.cpp use the patch to fix it

    cd tcRackModules
    patch -p1 <../../../VCVRack-rpi/patches/tcRackModules_typo_fix.patch

Then build as normal

    git submodule update --init --recursive
    make dep
    make
    make install
