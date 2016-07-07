# android_local_manifest
Initial commit
Add into repo directory

Use this command to pull tesla-6.0 from (curl) to initialize this repo onto your local building pc

Don't forget to add in your tesla branch here before using the command below to sync my local manifest.


Pull tesla repo-->https://github.com/Tesla-M/manifest   Follow these instructions to get your build environment setup.

Then use this either after you repo sync or after you init the tesla-m repo.

curl --create-dirs -L -o .repo/local_manifests/local_manifest.xml -O -L https://raw.githubusercontent.com/vm03/android_local_manifest/cm-13.0/local_manifest.xml
