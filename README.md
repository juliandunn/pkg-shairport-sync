# shairport-sync Packaging for Raspberry Pi (Raspbian)

Packaging of [shairport-sync](https://github.com/mikebrady/shairport-sync) has
gotten significantly easier now that Raspbian is based on `debian/jessie`.
Basically, you can simply recompile the sources from the [Debian source tree](https://anonscm.debian.org/cgit/collab-maint/shairport-sync.git) and recompile
them using `debuild`. If it complains about a pinned `debhelper >= 11`
(because the debian packaging is written for a later version of Debian)
just remove the pin in `debian/control`.

## Building shairport-sync

You'll need to make sure you have a standard Debian package building
toolchain, `libsoxr` and `dh_systemd` packages installed. Then it's just
a matter of:

1. Check out the [Debian source tree](https://anonscm.debian.org/cgit/collab-maint/shairport-sync.git)
2. Put the source tarball of `shairport-sync` in the parent directory
3. Build the package as normal using `dpkg-buildpackage -us -uc`

## Do You Just Want The Binaries?

Get them from my [Bintray repo](https://bintray.com/juliandunn/deb/shairport-sync/view)
