# Maintainer <me@xananax.com>
pkgname=qtodotxt2
pkgver=2.0.0
pkgrel=1
pkgdesc="cross-platform UI client for todo.txt files QTodoTxt2 is a cross-platform UI client for todo.txt files. It allows you to manage projects, contexts in a GTD way. You can use it on Linux, Windows, Mac OS X. Your todo.txt file can be sync with Dropbox, Owncloud or what you want, it's just a text file ! This is the rewritten version 2."
arch=("any")
url="http://qtodotxt.org/"
license=('GPL')
depends=('python' 'python-pyqt5' 'qt5-declarative' 'qt5-quickcontrols')
provides=("qtodotxt2")
install=$pkgname.install
source=("$pkgname-$pkgver.tar.gz::https://github.com/QTodoTxt/QTodoTxt2/archive/$pkgver.tar.gz" "$pkgname-$pkgver.ico::https://raw.githubusercontent.com/QTodoTxt/QTodoTxt/master/qtodotxt/ui/resources/qtodotxt.ico")
md5sums=("a1af7b8f9e490e908748665461165291" "795923c66fe30d69b30b10e1eacaff8f")

package() {
  cd "$srcdir/QTodoTxt2-$pkgver"
  install -Dm755 bin/qtodotxt $pkgdir/usr/share/qtodotxt2/bin/qtodotxt2
  cp -pr qtodotxt2 "$pkgdir/usr/share/qtodotxt2/"
  install -Dm644 "$srcdir/$pkgname-$pkgver.ico" "${pkgdir}/usr/share/qtodotxt2/artwork/icon/qTodo-512.png"
  install -Dm644 packaging/Debian/qtodotxt.desktop "${pkgdir}/usr/share/applications/qtodotxt2.desktop"
  sed -i 's/Exec=qtodotxt %u/Exec=qtodotxt2 %u/g' "${pkgdir}/usr/share/applications/qtodotxt2.desktop"
  mkdir -p $pkgdir/usr/bin/
  ln -s /usr/share/qtodotxt2/bin/qtodotxt2 $pkgdir/usr/bin/qtodotxt2
}