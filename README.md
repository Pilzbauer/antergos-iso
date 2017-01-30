Modified version of Antergos ISO with included nvidia driver to install it with a GTX 970.

## Dependencies ##

- antergos-gfxboot for a graphical boot (or isolinux/syslinux)
- arch-install-scripts
- dosfstools
- libisoburn
- mkinitcpio-nfs-utils
- make
- openfonts (https://www.archlinux.org/packages/community/any/opendesktop-fonts/download/)
- patch
- squashfs-tools
- wget

## Instructions ##

 - `sudo make install`
 - Copy the antergos folder from `/usr/share/antergos-iso/configs` to your working directory (`/var/tmp/antergos`, for instance).
 - Clone antergos-gfxboot : `git clone https://github.com/antergos/antergos-gfxboot /var/tmp/antergos/antergos-gfxboot`
 (or setup isolinux/syslinux).
 - Create destination folder `/out` : `sudo mkdir /out`
 - Create a symlink to your working directory and call it `/start` : `sudo ln -s /var/tmp/antergos /start`
 - Download openfonts (see dependencies) and move it to `/start`
 - Build the iso (run the command inside the `/var/tmp/antergos/configs/antergos` directory): `sudo ./build.sh build dual`

/start and /out are defaults. You can change it passing the desired directories as parameters to build.sh

If you want to try to build the iso again, please remember to clean all generated files first: `sudo ./build.sh clean`
