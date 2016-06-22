pkgname=duolingo
pkgver=0.3.1
pkgrel=1
pkgdesc="Unofficial release of Duolingo for Linux / Learn languages by playing a game. It's 100% free, fun, and scientifically proven to work."
url="https://www.duolingo.com/"
arch=('x86_64')
license=('custom')
install=duolingo.install
source=("https://github.com/mikethedj4/duolingo-linux/raw/master/${pkgname}-linux.tar.gz"
        "Duolingo.desktop")
md5sums=('b69a84ad08080a851c517496ddd4e785'
         '81038bee242ba1175f0a57b7dd585b8f')

package() {
    cd "$srcdir/Duolingo/resources/default_app/icons"
  for y in 16 32 64 128; do
    install -Dm644 ${y}.png "$pkgdir"/usr/share/icons/hicolor/${y}x${y}/apps/duolingo.png
    install -Dm644 logo.svg "$pkgdir"/usr/share/pixmaps/duolingo.svg
  done
    rm -r ../icons && cd "$srcdir"/Duolingo/
    install -Dm755 electron "$pkgdir"/opt/duolingo/duolingo
    install -Dm644 LICENSE "$pkgdir"/usr/share/licenses/duolingo/LICENSE
    install -Dm644 "$srcdir"/Duolingo.desktop "$pkgdir"/usr/share/applications/Duolingo.desktop
    cp -r {locales,resources,*.*,version} "$pkgdir"/opt/duolingo/
}
