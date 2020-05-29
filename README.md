# InyTag
TagLib For Valac

## Mp3, Mp4, Flac.
## Repo.

    sudo add-apt-repository ppa:torik-habib/inytags
    sudo apt-get update
    sudo apt-get install inytag

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

    var file_mp4 = new InyTag.Mp4_File (//file music m4a path);
    file_mp4.mp4_tag.title = string;
    file_mp4.mp4_tag.artist = string;
    file_mp4.mp4_tag.album = string;
    file_mp4.mp4_tag.genre = string;
    file_mp4.mp4_tag.comment = string;
    file_mp4.mp4_tag.year = (uint);
    file_mp4.mp4_tag.track = (uint);
    file_mp4.set_picture (InyTag.Format_Type.JPEG, //file image path);
    file_mp4.save ();
