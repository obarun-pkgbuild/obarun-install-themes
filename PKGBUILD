# Maintainer: Eric Vidal <eric@obarun.org>


pkgname=obarun-install-themes
_commit=9c38a461c176ec8829372c52061551a821c7fafe # tag 0.0.4
pkgver=0.0.4
pkgrel=1
pkgdesc="Templates for automatic installation by obarun-install"
arch=(x86_64)
url="https://github.com/Obarun/obarun-install-themes"
license=(BEERWARE)
depends=(obarun-install)
#source=("obarun-install-themes::git+https://github.com/Obarun/obarun-install-themes#tag=v${pkgver}")
source=("git+https://github.com/Obarun/obarun-install-themes#commit=$_commit")
md5sums=(SKIP)
validpgpkeys=('6DD4217456569BA711566AC7F06E8FDE7B45DAAC') # Eric Vidal

package() {
	cd "$srcdir/$pkgname"
	
	install -dm 0755 "$pkgdir/usr/share/licenses/obarun-install-themes/"
	install -Dm 0644 "LICENSE" "$pkgdir/usr/share/licenses/obarun-install-themes/LICENSE"
	install -Dm 0644 "PKGBUILD" "$pkgdir/var/lib/obarun/obarun-install-themes/update_package/PKGBUILD"

	# make a loop for all present directories
	for k in jwm openbox plasma xfce4;do
		install -Dm 0755 "$k/customizeChroot" "$pkgdir/var/lib/obarun/obarun-install/config/$k/customizeChroot"
		install -Dm 0644 "$k/pacman.conf" "$pkgdir/var/lib/obarun/obarun-install/config/$k/pacman.conf"
		for i in $k/package_list/*;do
			install -Dm 0644 "$i" "$pkgdir/var/lib/obarun/obarun-install/config/$i"
		unset i
		done
		cp -aT "$k/rootfs" "$pkgdir/var/lib/obarun/obarun-install/config/$k/rootfs"	
	unset k
	done   
	
}
