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

## computerscare
computerscare doesn't default to the v2.0.4 branch so it will need to be checked out

    git clone --branch v2.0.4 https://github.com/freddyz/computerscare-vcv-modules.git
    

Then build as normal

    cd computerscare-vcv-modules
    git submodule update --init --recursive
    make dep
    make
    make install

## LSFR
LSFR doesn't default to the 2.0 branch so it will need to be checked out

    git clone --branch V2X https://github.com/alto777/LFSR.gi

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

    git clone --branch master-V2 https://github.com/knchaffin/Meander.gi

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

## Valley
Valley requires borrowing some header files from the Cardinal project to build on the Raspberry Pi

Clone the Cardinal repo outside your rack repo folder

    git clone --depth 1 https://github.com/DISTRHO/Cardinal.git

Go into the plugins subfolder and clone the Valley repo.  When you build the plugin, you need to reference the simd-compat folder from the Cardinal source.  Replace "~/src" with the parent directory of your Cardinal repo clone.
  
    cd ./Rack/plugins
    git clone --depth 1 https://github.com/ValleyAudio/ValleyRackFree.git
    cd ValleyRackFree
    git submodule update --init --recursive
    make CXXFLAGS="-I ~/src/Cardinal/include/simd-compat/" dep
    make CXXFLAGS="-I ~/src/Cardinal/include/simd-compat/"
    make install


