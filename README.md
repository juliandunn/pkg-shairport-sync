# shairport-sync Packaging for Raspberry Pi (Raspbian)

Packaging of [shairport-sync](https://github.com/mikebrady/shairport-sync) has
gotten significantly easier now that Raspbian is based on `debian/buster`.
Basically, you can simply recompile the sources from the [Debian source tree](https://salsa.debian.org/debian/shairport-sync.git) and recompile
them using `debuild`.

## Building shairport-sync

You'll need to make sure you have a standard Debian package building
toolchain and `dh_systemd` packages installed. Then it's just
a matter of:

1. Check out the [Debian source tree](https://salsa.debian.org/debian/shairport-sync)
2. Put the source tarball of `shairport-sync` in the parent directory
3. Build the package as normal using `dpkg-buildpackage -us -uc`

## Do You Just Want The Binaries?

Get them from my [Bintray repo](https://bintray.com/juliandunn/deb/shairport-sync/view)
