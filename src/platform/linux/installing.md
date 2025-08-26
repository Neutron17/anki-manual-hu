# Az Anki telepítése és frissítése Linux-on
<a id="Installing & Upgrading Anki on Linux"></a>

<!-- toc -->

## Telepítési Követelmények
<a id="Requirements"></a>

The packaged version requires a recent 64 bit Intel/AMD Linux with glibc, and common
libraries like libwayland-client and systemd. If you are on a different
architecture (e.g ARM/AArch64), or a barebones Linux distro, you will not be able to use the
packaged version, but you may be able to use the [Python wheels](https://betas.ankiweb.net/#via-pypipip)
instead.

Debian(alapú) rendszereken (mint pl. az Ubuntu), és [Linux-os Chromebook-okon](https://support.google.com/chromebook/answer/9145439?), futtasd le a következő parancsot
a telepítés megkezdése előtt:

```shell
sudo apt install libxcb-xinerama0 libxcb-cursor0 libnss3
```

Ha az Anki nem tud lefutni telepítés után, lehet hogy [hiányoznak más segédkönyvtárak](./missing-libraries.md).

Hogyha Ubunti 24.04-en vagy, és nem tudod lefuttatni az Anki-t, olvasd el [ezt az angol nyelvű oldalt](https://forums.ankiweb.net/t/issues-running-on-ubuntu-24-04/40974)!

Az Anki csak a glibc-vel működik, a musl-alapú disztribúciókon jelenleg nem fog működni.

## Telepítés

Az Anki telepítéséhez:

1. Töltsd le az Anki-t a <https://apps.ankiweb.net>-ről a Downloads(letöltések) mappába.
2. Ha a zstd nincs letöltve a rendszereden, le kell majd telepítened (pl: `sudo apt install zstd`)
3. Nyitsd meg a terminálodat, és futtasd le a következő parancsokat, a fájl/mappaneveket persze írd át megfelelőkre.

```shell
tar xaf Downloads/anki-launcher-2XXX-linux.tar.zst
cd anki-launcher-2XXX-linux
sudo ./install.sh
```

Egyes Linux rendszereken lehet, hogy más paramétereket kell használnod: `tar xaf --use-compress-program=unzstd`

4. Ezek után úgy futtathatod az Anki-t, hogy beírod a terminálba, hogy `anki` majd <kbd>Enter</kbd>-t nyomsz.
   Hogyha valamilyen problémába ütköznél, nézd meg a bal oldalt lévő linkeket.

## Upgrading

If you were running Anki from a .deb/.rpm/etc in the past, please make
sure to remove the system version before installing the package
provided here.

If you're upgrading from a previous package, simply repeat the
installation steps to upgrade to the latest version. Your user data
will be preserved.

If you wish to downgrade to a previous version, please make sure you
[downgrade first](http://changes.ankiweb.net).

## Add-on Compatibility

Some add-ons may not always work with the latest Anki release. If you upgrade to
the latest Anki version and find an add-on you cannot live without stops working,
you can download older Anki versions from the [releases page](https://github.com/ankitects/anki/releases).

## Problems

If you encounter any issues when installing or starting Anki, please see the
following pages:

- [Missing Libraries](missing-libraries.md)
- [Display Issues](display-issues.md)
- [Blank Main Window](blank-window.md)
- [Linux Distro Packages](distro-packages.md)
- [Incorrect GTK Theme](gtk-theme.md)
- [Wayland](wayland.md)
- [Input Methods](input-methods.md)
