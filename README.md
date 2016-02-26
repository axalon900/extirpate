# Extirpate
"extirpate" is a script for expunging symbols from a universal static library.

I wrote this script as a response to some static iOS frameworks in my project containing symbols from other third party libraries that my app was also using. This is an annoying issue, as it causes either several "duplicate symbol" errors (if statically linked) or some runtime collisions (if dynamically linked). So, since using lipo to unpack each architecture, manually delete the appropriate object files for each architecture, rebuild the static lib for each architecture, and repacking the fat binary is very tedious, I wrote this to do it all for me.

The script is a bit spartan, but I figure someone else might find this little thing useful. :)

## Requirements

As far as I know, this only works on OS X, but the script uses the following to do its job:

* bash
* coreutils
* lipo
* egrep
* libtool
* ar

