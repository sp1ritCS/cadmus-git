# Maintainer: sp1rit <sp1ritCS@pm.me>
pkgname=cadmus-git
pkgver=0.0.1
pkgrel=1
pkgdesc="A GUI frontend for @werman's Pulse Audio real-time noise suppression plugin "
arch=("any")
url="https://github.com/josh-richardson/cadmus/"
license=("GPL-3.0")
depends=("python" "python-fbs" "python-pulsectl" "noise-suppression-for-voice" "python-pyqt5" "python-pyqt5-sip")
makedepends=()
provides=("${pkgname%-git}")
source=("${pkgname%-git}::git+https://github.com/josh-richardson/cadmus.git"
        "${pkgname%-git}-$pkgver.patch")
md5sums=("SKIP"
         "389688275dd901366889a67c38076051") #generate with 'makepkg -g'

prepare() {
	cd "$srcdir/${pkgname%-git}"
    patch -p1 -i "$srcdir/${pkgname%-git}-$pkgver.patch"
}

package() {
	cd "$srcdir/${pkgname%-git}"
    install -Dm755 $srcdir/${pkgname%-git}/src/main/python/main.py "$pkgdir/usr/bin/cadmus"
}
