# Maintainer: Limao Luo <luolimao+AUR@gmail.com>

pkgname=wallpaperfiner
pkgver=0.94
pkgrel=3
pkgdesc="A small and easy to use utility which adjusts images to fit your desktop size"
arch=(i686 x86_64)
url=http://hyperprog.com/wpfiner
license=(GPL2)
depends=(qt4)
source=($url/wpfiner-source-$pkgver.zip
    $pkgname.desktop)
sha256sums=('66513c878d5d2bf6c4d68d26c0959cd307bbfb0377d9bf119f01e4df02c18ae7'
    'e68a1facedd1c9387c16510be49b84a9a2c56ae8e5521047cd454ae765de5f1c')
sha512sums=('a98678286a01560a949dc877bea11c008914c1dba1521e2d21279e15d0084374bb342bdbf8d1cf92c48aa3c654d53289f99afc717b11860bac7c28fe02325815'
    '327462977d20e086e5a6d475219b58b649775e9ef6476eabe86529fbbcad69a5d6405f138feb57172d1ad6e56cf6c6b7dd975a9be2acc35ea88f583ac431be10')

build() {
    cd WallpaperFiner/
    qmake-qt4 -makefile
    make
}

package() {
    cd WallpaperFiner/
    install -Dm755 $pkgname "$pkgdir"/usr/bin/$pkgname
    install -Dm644 wpfiner.png "$pkgdir"/usr/share/pixmaps/$pkgname.png
    desktop-file-install ../$pkgname.desktop --dir "$pkgdir"/usr/share/applications/
}
