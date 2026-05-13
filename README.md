This is a set of instructions to build a buildroot image to be used for v86. This variation fo the process was designed to create two different files - bzimage and cpio formats.

This does not follow David Humphreys browservm project. That project does a nice job of packaging all of the processes together as one, under a docker container. However, it
makes the build process long and brittle. If any part of the OS changes, you have to go back and rebuild the whole thing.

We are focused here on building these two components:

* bzimage file - this is the boot file, drivers, etc. We probably only want to build this once.
* cpio file - this is the file system that we want to build out again and again.

Props to Dhrupad Joshi https://github.com/trigerman/ for pulling this together.
