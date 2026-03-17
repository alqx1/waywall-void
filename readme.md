# Waywall (on Void Linux)

This project holds the templates to build Waywall on Void Linux.

## Installation

1. Make sure you have already cloned the void-packages repository somewhere on your disk and have bootstrapped the binary.

```{sh}
git clone https://github.com/void-linux/void-packages
cd void-packages
./xbps-src binary-bootstrap
cd ..
```

2. Next clone this repository.

```sh
git clone https://github.com/alqx1/waywall-void.git
cd waywall-void
```

3. Move the source packages from the repository to the main packages.

```sh
cp -r waywall-void/srcpkgs/* void-packages/srcpkgs/
```

4. Append waywall's shlibs to void-packages'.

```sh
cat waywall-void/common/shlibs >> void-packages/common/shlibs
```

5. Build the packages and install them.

```sh
cd void-packages
./xbps-src pkg libspng
./xbps-src pkg waywall
sudo xbps-install -R hostdir/binpkgs waywall
# or if you have xtools installed
sudo xi -f waywall
```
