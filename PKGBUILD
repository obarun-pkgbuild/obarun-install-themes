# Maintainer: Eric Vidal <eric@obarun.org>


pkgname=obarun-install-themes
_commit=254b558f81505c7639d251301d88c25367e9f874 # tag 0.0.6
pkgver=0.0.6
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
