pkgname=dfw
pkgver=0.1.0
pkgrel=1
pkgdesc="CLI tool accepting ufw-like commands to create firewall rules that docker will respect."
arch=('any')
depends=('python' 'docker' 'iptables')
source=("$pkgname")
sha256sums=(90361c2df311c96c8504b2dc0195f44247dc4ca9ff3e6605de95311e071efe65)

package() {
    install -Dm755 "$srcdir/$pkgname" "$pkgdir/usr/bin/$pkgname"
    install -d -m755 "$pkgdir/etc/$pkgname"
}
