zu
==

Unzipper (in the tradition of `uz`, but better). Works for .tgz, .xz, .zip,
you name it.

If you have an archive sitting there, `zu foo.xyz` should take care of it.

It will:

- Know how to extract the archive (based on extension ┈ though a version that
  detects based on `file` is something I'm considering) 
- Guard against impoliteness. That is, if the archive only has one file, it
  will be permitted to extract into the current directory, otherwise it will
  first `mkdir foo; cd foo` then extract there. (The directory name will be
  the archive file minus the extension.)
- Remove the archive file if you pass `-d`

Dependencies
------------

`zu` doesn't strive to be dependency-free by any means.

For starters, it expects Ruby.

Then it simply delegates to `unzip`, `gunzip`, `tar`, etc.

I should probably make it smarter, e.g. have a `zu --checkdeps` command to
tell you which programs you might need. Consider it a TODO (which you can
boost by making a request. (Or a Pull Request!))

Installation
------------

It's a standalone script, so putting the `bin/zu` file somewhere in your
`$PATH` will do the trick, but I definitely recommend using
[`...`](http://github.com/ingydotnet/....git) for this, and for dotfile/script
management as a whole.
