# InyTag
TagLib For Valac
## Mp3, Mp4, Flac.

## Building, Testing, and Installation
## You'll need the following dependencies:

* meson
* libtag1-dev

Run `meson` to configure the build environment and then `ninja` to build and run automated tests

    meson build --prefix=/usr
    cd build
    ninja

To install, use `ninja install`

    sudo ninja install

Example write with valac:
M4a Tag write;
var file_mp4 = new InyTag.Mp4_File (//set path location);
file_mp4.mp4_tag.title =
file_mp4.save ();
