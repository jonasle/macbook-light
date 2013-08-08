#Maintainer: Jonas Lejeune	<archlinux@jonaslejeune.be>

pkgname=mblight
pkgver=0.1
pkgrel=1
pkgdesc='Setup keyboard- and screenbacklight using the light sensor of a Macbook'
url='https://github.com/jonasle/macbook-light'
license=('GPL')
arch=('any')
depends=('bash')
makedepends=('git')

_gitroot=git@github.com:jonasle/macbook-light.git
_gitname=macbook-light

build()
{
	cd $srcdir

	msg "Connecting to git server"

	if [ -d $srcdir/$_gitname ] ; then
		cd $_gitname && git pull origin
		msg "The local files are updated."
	else
	  git clone $_gitroot
	fi
}

package()
{	
	cd "$srcdir/$_gitname"

	install -Dm 755 $srcdir/$_gitname/$pkgname $pkgdir/usr/bin/$pkgname
	install -Dm 755 $srcdir/$_gitname/${pkgname}.service $pkgdir/etc/systemd/system/${pkgname}.service
}
