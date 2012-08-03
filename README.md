zu
==

Unzipper (in the tradition of `uz`, but better). Works for .tgz, .xz, .zip,
you name it. (Literally. If you find an archive that it doesn't open, let me
know about it and I'll add that.)

If you have an archive sitting there of format `xyz`, then `zu foo.xyz` should
take care of it.

It will:

- Know how to extract the archive (based on extension ┈ though a version that
  detects based on `file` is something I'm considering)
- Guard against impoliteness. That is, if the archive only has one file, it
  will be permitted to extract into the current directory, otherwise it will
  first `mkdir foo; cd foo` then extract there. (The directory name will be
  the archive file minus the extension.)
- Download the file first, using `wget`, if the arg starts with `http:`,
  `https:`, or `ftp:`
- Remove the archive file if you pass `-d`

Dependencies
------------

`zu` doesn't strive to be dependency-free by any means.

For starters, it expects Ruby.

Then it simply delegates to `unzip`, `gunzip`, `tar`, etc.

Not sure if I ever plan on changing this. The main purpose is to optimize the
command-line extraction of archives on a configured box.

Installation
------------

It's a standalone script, so putting the `bin/zu` file somewhere in your
`$PATH` will do the trick, but I definitely recommend using
[`...`](http://github.com/ingydotnet/....git) for this, because it's cool.

Anything
--------

Tell me. (rking-zu@sharpsaw.worg)[mailto:rking-zu@sharpsaw.org]
