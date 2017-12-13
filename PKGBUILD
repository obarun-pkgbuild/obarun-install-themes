# Maintainer: Eric Vidal <eric@obarun.org>


pkgname=obarun-install-themes
_commit=41c6f0a082df4ba4099a9637cfdaa5062544875d # tag 0.0.7
pkgver=0.0.7
pkgrel=1
pkgdesc="Templates for automatic installation by obarun-install"
arch=(x86_64)
url="https://github.com/Obarun/obarun-install-themes"
license=(ISC)
depends=(obarun-install)
#source=("obarun-install-themes::git+https://github.com/Obarun/obarun-install-themes#tag=v${pkgver}")
source=("git+https://github.com/Obarun/obarun-install-themes#commit=$_commit")
md5sums=(SKIP)
validpgpkeys=('6DD4217456569BA711566AC7F06E8FDE7B45DAAC') # Eric Vidal

pkgver() {
	cd "${pkgname}"
	
	git describe --tags | sed -e 's:-:+:g;s:^v::'
}

package() {
	cd "${pkgname}"

	make DESTDIR="$pkgdir" install
}
