# Maintainer: TDY <tdy@gmx.com>

pkgname=parole
pkgver=0.2.0.6
pkgrel=1
pkgdesc="A modern media player based on the GStreamer framework"
arch=('i686' 'x86_64')
url="http://goodies.xfce.org/projects/applications/parole/"
license=('GPL')
depends=('gstreamer0.10-base>=0.10.11' 'hicolor-icon-theme' 'libnotify>=0.4.1' 
         'libxfcegui4>=4.6.0' 'taglib>=1.4')
makedepends=('pkgconfig>=0.9.0' 'xfce4-dev-tools')
optdepends=('xulrunner>=1.9.1: browser plugin')
conflicts=('parole-media-player-git')
options=('!libtool')
install=parole.install
source=(http://archive.xfce.org/src/apps/$pkgname/${pkgver%.*.*}/$pkgname-$pkgver.tar.bz2)
md5sums=('5d7e5ab7535bdf89508a8d7e551f9187')

build() {
  cd "$srcdir/$pkgname-$pkgver"
  ./configure --prefix=/usr --libexecdir=/usr/lib --enable-taglib --enable-libnotify
  make
}

package() {
  cd "$srcdir/$pkgname-$pkgver"
  make DESTDIR="$pkgdir" install
}
