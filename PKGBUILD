# Maintainer: Luka Dornhecker <luka.dornhecker@googlemail.com>
pkgname=mangashare-git
pkgver=20120601
pkgrel=1
pkgdesc="A simple downloader for mangashare.com"
arch=('any')
url="https://github.com/lukad/mangashare.py"
license=('GPL')
depends=('python3')
makedepends=('git')
provides=('mangashare')

_gitroot="git://github.com/lukad/mangashare.py.git"
_gitname="mangashare.py"

build() {
 	cd ${srcdir}
 	msg "Connecting to GIT server..."
 	
 	if [ -d mangashare.py ] ; then
 		cd mangashare.py && git pull origin
 		msg "The local files are updated."
 	else
 		git clone ${_gitroot}
 	fi

 	msg "GIT Checkout done"
 	msg "Starting make..."

 	cd ${srcdir}/${_gitname}

 	install -D -m755 mangashare ${pkgdir}/usr/bin/mangashare || return 1
}
