# shairport-sync Packaging for Raspberry Pi (Raspbian)

Packaging of [shairport-sync](https://github.com/mikebrady/shairport-sync) has
gotten significantly easier now that Raspbian is based on `debian/jessie`.
Basically, you can simply recompile the sources from the [Debian source tree](https://anonscm.debian.org/cgit/collab-maint/shairport-sync.git) and recompile
them using `debuild`. If it complains about a pinned `debhelper >= 11`
(because the debian packaging is written for a later version of Debian)
just remove the pin in `debian/control`.

## Do You Just Want The Binaries?

Get them from my [Bintray repo](https://bintray.com/juliandunn/deb/shairport-sync/view)
