# Maintainer: Arch Haskell Team <arch-haskell@haskell.org>
_hkgname=minesweeper
pkgname=minesweeper
pkgver=0.9
pkgrel=2
pkgdesc="Minesweeper game which is always solvable without guessing"
url="http://hackage.haskell.org/package/${_hkgname}"
license=('custom:BSD3')
arch=('i686' 'x86_64')
makedepends=('ghc' 'haskell-binary<0.6' 'haskell-binary-generic<0.3' 'haskell-bytestring=0.9.1.7' 'haskell-cairo<0.12' 'haskell-containers=0.3.0.0' 'haskell-directory=1.0.1.1' 'haskell-filepath=1.1.0.4' 'haskell-glade<0.12' 'haskell-gtk<0.12' 'haskell-random=1.0.0.2' 'haskell-time')
depends=('gmp')
options=('strip')
source=(http://hackage.haskell.org/packages/archive/${_hkgname}/${pkgver}/${_hkgname}-${pkgver}.tar.gz)
build() {
    cd ${srcdir}/${_hkgname}-${pkgver}
    runhaskell Setup configure --prefix=/usr --docdir=/usr/share/doc/${pkgname} -O
    runhaskell Setup build
}
package() {
    cd ${srcdir}/${_hkgname}-${pkgver}
    runhaskell Setup copy --destdir=${pkgdir}
    install -D -m644 LICENSE ${pkgdir}/usr/share/licenses/${pkgname}/LICENSE
    rm -f ${pkgdir}/usr/share/doc/${pkgname}/LICENSE
}
md5sums=('0f65fead2190e4d72483e92d8f431134')
