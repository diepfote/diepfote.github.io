Package manager helpers

#### Table of contents

1. [Brew](#darwin--mac-os---brew)
    - [brew formulae-require](#brew-formulae-require)
    - [brew required-by](#brew-required-by)
    - [brew leaves-require](#brew-leaves-require)
2. [Yay and Pacman](#arch-linux---yay-and-pacman)
    - [Pacman Throttle Bandwidth](#pacman-throttle-bandwidth)
    - [yay-all](#yay-all)
    - [yay-generate-PKGBUILD-checksum](#yay-generate-pkgbuild-checksum)
        * [Why?  ](#why)


# Darwin / Mac OS - brew

## brew formulae-require

[find here](https://github.com/diepfote/scripts/blob/20e3c1d8f566180e500e9dff28ee5914c090a3ee/bin/darwin/brew-formulae-require)

What does `curl` depend on?
```
$ brew formulae-require curl
curl: brotli ca-certificates gettext libidn2 libnghttp2 libssh2 libunistring openldap openssl@1.1 zstd
```

## brew required-by

[find here](https://github.com/diepfote/scripts/blob/20e3c1d8f566180e500e9dff28ee5914c090a3ee/bin/darwin/brew-required-by)
  
Which packages require `gettext`?

*Hint*: Highlights the package you were looking for (not shown here).

```
$ brew required-by gettext
cairo: ca-certificates fontconfig freetype gdbm gettext glib libffi libpng libpthread-stubs libx11 libxau libxcb libxdmcp libxext libxrender lzo mpdecimal openssl@1.1 pcre pixman pkg-config python@3.9 readline sqlite xorgproto xz
ffmpeg: aom bdw-gc brotli ca-certificates cairo cjson cmocka dav1d flac fontconfig freetype frei0r fribidi gdbm gettext giflib glib gmp gnutls gobject-introspection graphite2 guile harfbuzz icu4c imath jpeg jpeg-xl lame leptonica libarchive libass libb2 libbluray libevent libffi libidn2 libnghttp2 libogg libpng libpthread-stubs librist libsamplerate libsndfile libsodium libsoxr libtasn1 libtiff libtool libunistring libvidstab libvmaf libvorbis libvpx libx11 libxau libxcb libxdmcp libxext libxrender little-cms2 lz4 lzo m4 mbedtls mpdecimal nettle opencore-amr openexr openjpeg openssl@1.1 opus p11-kit pcre pixman pkg-config python@3.9 rav1e readline rubberband sdl2 snappy speex sqlite srt tesseract theora unbound webp x264 x265 xorgproto xvid xz zeromq zimg zstd
...
```

## brew leaves-require

[find here](https://github.com/diepfote/scripts/blob/20e3c1d8f566180e500e9dff28ee5914c090a3ee/bin/darwin/brew-leaves-require)

Shows all dependencies for all leaf packages:

```
$ brew leaves-require
...
pango: ca-certificates cairo fontconfig freetype fribidi gdbm gettext glib gobject-introspection graphite2 harfbuzz icu4c libffi libpng libpthread-stubs libx11 libxau libxcb libxdmcp libxext libxrender lzo mpdecimal openssl@1.1 pcre pixman pkg-config python@3.9 readline sqlite xorgproto xz
qemu: bdw-gc ca-certificates gdbm gettext glib gmp gnutls guile jpeg libevent libffi libidn2 libnghttp2 libpng libslirp libssh libtasn1 libtool libunistring libusb lzo m4 mpdecimal ncurses nettle openssl@1.1 p11-kit pcre pixman pkg-config python@3.9 readline snappy sqlite unbound vde xz
...
```




# Arch Linux - yay and pacman

## Pacman Throttle Bandwidth

If you are on a slow internet connection and you do not want to break
internet access for anyone else on the network (or yourself for that matter)
you need to throttle `pacman` and `yay`.  
This is why I wrap both commands. They are throttled or unthrottled based on
the file `/tmp/pacman-bandwidth-limit`.

* [`pacman`](https://github.com/diepfote/scripts/blob/1db0a8c5715fdba6897987422d7725f50de8fdd8/bin/linux/pacman#L65-L72)
* [`yay`](https://github.com/diepfote/scripts/blob/8b597bb25948b2aebba4643834e7cb49b3ff45af/bin/linux/yay#L48-L55)

This is implemented via [trickle](https://github.com/mariusae/trickle).

## yay-all

[find here](https://github.com/diepfote/scripts/blob/20e3c1d8f566180e500e9dff28ee5914c090a3ee/bin/linux/yay-all)

- downloads new official packages (runs `pacman -Syu`)
- then executes `yay -G <pkg-name` (updates PKGBUILD)
- generates a checksum for the updated PKGBUILD to check if it matches the manually generated checksum
- if it matches it starts an automated update (root privileges required, single time sudo approval)
- it does this ^ for a list of packages defined in `pkgs_with_saved_checksums=()`
- afterwards it runs a normal `yay` upgrade and asks the user if he/she want to upgrade the remaining packages

## yay-generate-PKGBUILD-checksum

[find here](https://github.com/diepfote/scripts/blob/20e3c1d8f566180e500e9dff28ee5914c090a3ee/source-me/linux/posix-compliant-shells.sh#L289)

This supplements yay-all. It generates checksums for AUR PKGBUILDs.

### Why?  

A PKGBUILD contains a checksum and pkg version section. 
These alter the checksum generated for a PKGBUILD anytime there is a version update.
The point of this function/script is to ignore changes unless instructions in a given PKGBUILD change.

