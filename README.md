# shairport-sync Packaging for Raspberry Pi (Raspbian)

Here's how I create native Debian packages for [shairport-sync](https://github.com/mikebrady/shairport-sync) which is the successor to Shairport.

## Get libsoxr

shairport-sync now depends on the presence of `libsoxr` for which there are no
packages in Raspbian. To get it, you can either check out the [tree](https://anonscm.debian.org/gitweb/?p=pkg-multimedia/libsoxr.git) and make a Debian package directly,
or just install the ones I have pre-built and [host on Bintray](https://bintray.com/juliandunn/deb/libsoxr/view).

## Patching and building shairport-sync

We're fortunate that shairport-sync is now a fairly up-to-date distro-maintained
package. Unfortunately the [Debian package](https://tracker.debian.org/pkg/shairport-sync) is now using systemd and Raspbian doesn't support that, nor does Raspbian
have the /lib/init/init-d-functions library that makes scripts in /etc/init.d
much less cluttered.

Thus, to build the package for Raspbian, do the following:

1. Check out the [Debian source tree](https://anonscm.debian.org/cgit/collab-maint/shairport-sync.git)
2. Edit the `debian/control` file to remove the dependency on systemd
3. Replace the `debian/shairport-sync.init` file with the one in this repository
4. Build the package as normal using `dpkg-buildpackage -us -uc`

## Do You Just Want The Binaries?

Get them from my [Bintray repo](https://bintray.com/juliandunn/deb/shairport-sync/view)
