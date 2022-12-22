Florian Begusch's package manager helpers

# Darwin / Mac OS - brew

## [brew formulae-require](https://github.com/diepfote/scripts/blob/20e3c1d8f566180e500e9dff28ee5914c090a3ee/bin/darwin/brew-formulae-require)

What does `curl` depend on?
```
$ brew formulae-require curl
curl: brotli ca-certificates gettext libidn2 libnghttp2 libssh2 libunistring openldap openssl@1.1 zstd
```

## [brew required-by](https://github.com/diepfote/scripts/blob/20e3c1d8f566180e500e9dff28ee5914c090a3ee/bin/darwin/brew-required-by)
  
Which packages require `gettext`?

*Hint*: Highlights package you were looking for in output (does not show here).

```
$ brew required-by gettext
cairo: ca-certificates fontconfig freetype gdbm gettext glib libffi libpng libpthread-stubs libx11 libxau libxcb libxdmcp libxext libxrender lzo mpdecimal openssl@1.1 pcre pixman pkg-config python@3.9 readline sqlite xorgproto xz
ffmpeg: aom bdw-gc brotli ca-certificates cairo cjson cmocka dav1d flac fontconfig freetype frei0r fribidi gdbm gettext giflib glib gmp gnutls gobject-introspection graphite2 guile harfbuzz icu4c imath jpeg jpeg-xl lame leptonica libarchive libass libb2 libbluray libevent libffi libidn2 libnghttp2 libogg libpng libpthread-stubs librist libsamplerate libsndfile libsodium libsoxr libtasn1 libtiff libtool libunistring libvidstab libvmaf libvorbis libvpx libx11 libxau libxcb libxdmcp libxext libxrender little-cms2 lz4 lzo m4 mbedtls mpdecimal nettle opencore-amr openexr openjpeg openssl@1.1 opus p11-kit pcre pixman pkg-config python@3.9 rav1e readline rubberband sdl2 snappy speex sqlite srt tesseract theora unbound webp x264 x265 xorgproto xvid xz zeromq zimg zstd
...
```

## [brew leaves-require](https://github.com/diepfote/scripts/blob/20e3c1d8f566180e500e9dff28ee5914c090a3ee/bin/darwin/brew-leaves-require)

Shows all dependencies for all leaf packages:

```
$ brew leaves-require
...
pango: ca-certificates cairo fontconfig freetype fribidi gdbm gettext glib gobject-introspection graphite2 harfbuzz icu4c libffi libpng libpthread-stubs libx11 libxau libxcb libxdmcp libxext libxrender lzo mpdecimal openssl@1.1 pcre pixman pkg-config python@3.9 readline sqlite xorgproto xz
qemu: bdw-gc ca-certificates gdbm gettext glib gmp gnutls guile jpeg libevent libffi libidn2 libnghttp2 libpng libslirp libssh libtasn1 libtool libunistring libusb lzo m4 mpdecimal ncurses nettle openssl@1.1 p11-kit pcre pixman pkg-config python@3.9 readline snappy sqlite unbound vde xz
...
```




# Arch Linux - yay | pacman

## [yay-all](https://github.com/diepfote/scripts/blob/20e3c1d8f566180e500e9dff28ee5914c090a3ee/bin/linux/yay-all)

- downloads new official packages (runs `pacman -Syu`)
- then executes `yay -G <pkg-name` (updates PKGBUILD)
- generates checksum for updated PKGBUILD to check if it matches manually generated checksum.
- if it matches an automatic update is started (root privileges required, single time `sudo` approval)
- it does this ^ for a list of packages defined in `pkgs_with_saved_checksums=()`;
  afterwards it runs a normal `yay` upgrade and asks the user if he/she wants
  to upgrade the remaining packages

## [yay-generate-PKGBUILD-checksum](https://github.com/diepfote/scripts/blob/20e3c1d8f566180e500e9dff28ee5914c090a3ee/source-me/linux/posix-compliant-shells.sh#L289)

sublements `yay-all`, used to manually generate checksums for AUR PKGBUILDs

### Why?  

PKGBUILDS contain checksum and pkg versions sections. These alter the checksum
generated for a PKGBUILD anytime there is an update.
The point of this function/script is to not see checksum changes unless instructions
in a given PKGBUILD change.

