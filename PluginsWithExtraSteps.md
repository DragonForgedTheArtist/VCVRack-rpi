# Plugins That Require Extra Steps To Compile
The following plugins require extra steps to compile successfully.

## Valley
Valley requires borrowing some header files from the Cardinal project to build on the Raspberry Pi

Clone the Cardinal repo outside your rack repo folder

    git clone --depth 1 https://github.com/DISTRHO/Cardinal.git

Go into the plugins subfolder and clone the Valley repo.  When you build the plugin, you need to reference the simd-compat folder from the Cardinal source.  Replace "~/src" with the parent directory of your Cardinal repo clone.
  
    cd ./Rack/plugins
    git clone --depth 1 https://github.com/ValleyAudio/ValleyRackFree.git
    cd ValleyRackFree
    git submodule update --init --recursive --depth 1
    make CXXFLAGS="-I ~/src/Cardinal/include/simd-compat/" dep -j4
    make CXXFLAGS="-I ~/src/Cardinal/include/simd-compat/" -j4
    make install


