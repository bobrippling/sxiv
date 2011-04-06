sxiv: Simple (or small or suckless) X Image Viewer

sxiv is a really simple alternative to feh and qiv. Its only dependency besides
xlib is imlib2. The primary goal for writing sxiv is to create an image viewer,
which only implements the most basic features required for fast image viewing.
It works nicely with tiling window managers and its code base should be kept
small and clean to make it easy for you to dig into it and customize it for
your needs.

Installation
------------
sxiv is built using the commands:

    $ make
    # make install

Please note, that the latter one requires root privileges.
By default, sxiv is installed using the prefix "/usr/local", so the full path
of the executable will be "/usr/local/bin/sxiv".

You can install it into a directory of your choice by changing the second
command to:

    # PREFIX="/your/dir" make install

All build-time specific settings can be found in the file "config.h". Please
check and change them, so that they fit your needs.

Usage
-----
sxiv has two modes of operation: image and thumbnail mode. The default is image
mode, in which only the current image is shown. In thumbnail mode a grid of
small previews is displayed, making it easy to choose an image to open.

sxiv supports the following command-line options:

    -a           Display all given files, do not filter out unsupported files
                 (shorter startup time for long file list or slow file types)
    -d           Scale all images to 100%, but fit large images into window
    -F           Use size-hints to make the window fixed/floating
    -f           Start in fullscreen mode
    -g GEOMETRY  Set window position and size
                 (see section GEOMETRY SPECIFICATIONS of X(7))
    -p           Pixelize, i.e. turn off image anti-aliasing
    -q           Be quiet, disable warnings
    -r           Search given directories recursively for images
    -s           Scale all images to fit into window
    -t           Start in thumbnail mode
    -v           Print version information and exit
    -Z           Same as `-z 100'
    -z ZOOM      Scale all images to current zoom level, use ZOOM at startup

Use the following keys to control the basic behaviour of sxiv:

    q            Quit sxiv
    f            Toggle fullscreen mode (requires an EWMH/NetWM compliant
                 window manager)

Inside image view mode, the following key mappings are available:

    n,Space      Go to the next image
    p,Backspace  Go to the previous image
    g/G          Go to first/last image
    [/]          Go 10 images backward/forward
    +,=          Zoom in
    -            Zoom out
    0            Set zoom level to 100%
    w            Fit image into window
    h,j,k,l      Pan image left/down/up/right (also with arrow keys)
    <,>          Rotate image (counter-)clockwise by 90 degrees
    W            Resize window to fit image
    a            Toggle anti-aliasing
    A            Toggle visibility of alpha-channel, i.e. transparency
    r            Reload image
    D            Remove image from file list and go to next image
    Return       Switch to thumbnail mode

Additionally, the image view offers the following mouse commands:

    Button1           Go to the next image
    Button2           Drag image with mouse while keeping it pressed
    Button3           Go to the previous image
    ScrollUp          Pan image up
    ScrollDown        Pan image down
    Shift+ScrollUp    Pan image left
    Shift+ScrollDown  Pan image right
    Ctrl+ScrollUp     Zoom in
    Ctrl+ScrollDown   Zoom out

In thumbnail mode, the following key and mouse mappings are available:

    h,j,k,l      Move selection left/down/up/right (also with arrow keys)
    g/G          Move selection to first/last image
    D            Remove selected image from file list and select next image
    Return       Open selected image

    Button1      Select image/open image if it is already selected
    ScrollUp     Scroll up one row
    ScrollDown   Scroll down one row
