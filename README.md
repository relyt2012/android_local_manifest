# Building Android for Shamuuuu
This will aid you in building AOSP X for shamu

For starters you will need a build environment
I have used this guide for several years, however I use Linux Mint 
[Build Guide](https://nathanpfry.com/how-to-setup-ubuntu-16-04-lts-xenial-xerus-to-compile-android-roms/)

#### I also just found out that you'll need to add this also - After that guide above

```
sudo apt-get install openjdk-8-jdk android-tools-adb bc bison build-essential curl flex g++-multilib gcc-multilib gnupg gperf imagemagick lib32ncurses5-dev lib32readline-dev lib32z1-dev liblz4-tool libncurses5-dev libsdl1.2-dev libssl-dev libwxgtk3.0-dev libxml2 libxml2-utils lzop pngcrush rsync schedtool squashfs-tools xsltproc yasm zip zlib1g-dev git python
```

#### When you have that setup, you'll need to setup the repo you want to build - We are using AOSP X
#### Repo size for AOSP Extended is around 30-35GB
```
  repo init -u git://github.com/AospExtended/manifest.git -b 9.x
```

#### Before we sync, lets grab our device manifest!
```
  curl --create-dirs -L -o .repo/local_manifests/local_manifest.xml -O -L https://raw.githubusercontent.com/relyt2012/android_local_manifest/p-shamu/manifest.xml
```

#### Now that you have that, we are going to sync as they suggest here - [AOSPX](https://github.com/AospExtended/manifest/tree/9.x)
```
  repo sync -c -jx --force-sync --no-clone-bundle --no-tags
```

#### To build there are quite a few commands you can use, I try to get brunch working - So for the sake of this, I will be using brunch
```
  . build/envsetup.sh
  brunch_shamu-userdebug

  If that doesn't work, you can use lunch
  lunch aosp_shamu-userdebug
  mka -j4
```

#### If all is successful, you should be using your new rom! - Building takes some time though, it isn't something I'd recommend if you don't have much time as it is
#### With that said, good luck!!!!
