clipdf
======

Clip PDF files from the command line using the native PDF point coordinates.

## Requirements

- Linux (MacOSX might work)
- [Bash](https://www.gnu.org/software/bash/)
- [pdfinfo](http://linux.die.net/man/1/pdfinfo)
- [GhostScript](http://www.ghostscript.com/)

## Usage

`clipdf` is called from the command line with 6 required arguments:

```shell
$ clipdf INFILE PAGE LLX LLY URX URY
```

- `INFILE` is the input PDF file
- `PAGE` is the page number to clip from
- `LLX` and `LLY` are the X and Y coordinates (in points) of the
  lower-left corner of the box to clip
- `URX` and `URY` are the X and Y coordinates (in points) of the
  upper-right corner of the box to clip

By default, `clipdf` will output a PDF file using exactly those coordinates
and write it to a filename based on the input filename and the given
coordinates. The result can be affected by several options:

- `-o F` or `--output F` will write to F instead of the default filename
- `-r` or `--render` will produce a PNG file instead of a PDF
- `-m` or `--margin` will add a 1 point margin to the left, top, and right
  sides, and a 3 point margin to the bottom.

## Acknowledgments

These sources were very valuable in figuring out the commands to GhostScript:

- An AskUbuntu answer by user
  [bluenote10](http://askubuntu.com/users/161463/bluenote10):
    - http://askubuntu.com/a/592206
- Two StackOverflow answers by user
  [Kurt Pfeifle](http://stackoverflow.com/users/359307/kurt-pfeifle):
    - http://stackoverflow.com/a/6184547/1441112
    - http://stackoverflow.com/a/12485020/1441112
- The GhostScript reference:
    - http://ghostscript.com/doc/current/Use.htm
    - http://ghostscript.com/doc/current/Devices.htm
