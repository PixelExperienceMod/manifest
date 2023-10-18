# PixelExperience Plus for Redmi Note 10 Pro/Pro+/Discrovery (ruby) #
You can build PixelExperience thirteen-plus for ruby as follows.
### Sync ###

```bash
# Create directories
mkdir ~/android/pe
mkdir -p ~/android/ccache/pe

# Initialize local repository
cd ~/android/pe
repo init -u https://github.com/PixelExperience/manifest -b thirteen-plus

# Add local manifest
wget https://raw.githubusercontent.com/kasun-97/local_manifests/master/ruby/ruby_pe-13_roomservice.xml -P ~/android/pe/.repo/local_manifests/

# Sync
repo sync -c -j$(nproc --all) --force-sync --no-clone-bundle --no-tags
```

### Build ###

```bash
# Enable ccache
export USE_CCACHE=1 && export CCACHE_DIR=~/android/ccache/pe && export CCACHE_EXEC=/usr/bin/ccache && ccache -M 50G

# Set up environment
$ . build/envsetup.sh

# Choose a target
$ lunch aosp_ruby-userdebug

# Build the code
$ mka bacon -j$(nproc --all)
```
