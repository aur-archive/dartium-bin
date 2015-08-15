# Contributor: T. Jameson Little <t.jameson.little@gmail.com>
pkgname=dartium-bin
pkgver=1.10.0
pkgrel=1
pkgdesc="Chromium-based browser that includes the Dart virtual machine (integration version built with dart-editor)"
arch=(i686 x86_64)
url="http://www.dartlang.org/dartium/"
license=('BSD')
depends=('libudev.so.0' 'libgcrypt15' 'gconf')
optdepends=()
makedepends=(unzip)
provides=('dartium')
conflicts=('dartium')
replaces=()
install=
changelog=dartium.changelog
noextract=()

if [[ ${CARCH} = x86_64 ]]; then
	source=("http://storage.googleapis.com/dart-archive/channels/stable/release/latest/dartium/dartium-linux-x64-release.zip")
	md5sums=('cc2fd77e804b2c0b234f97fadd6cd333')
else
	source=("http://storage.googleapis.com/dart-archive/channels/stable/release/latest/dartium/dartium-linux-ia32-release.zip")
	md5sums=('e43ca49904f4860bf488eaed17b1ec22')
fi

package(){
	_from=dartium-lucid64-full-stable-45396.0
	mkdir -p ${pkgdir}/opt ${pkgdir}/usr/bin ${pkgdir}/usr/lib
	find ${srcdir}/${_from} -perm -u+x -exec chmod +x '{}' +
	find ${srcdir}/${_from} -perm -u+r -exec chmod +r '{}' +
	find ${srcdir}/${_from} -perm -u+w -exec chmod +w '{}' +
	cp -r ${srcdir}/${_from} ${pkgdir}/opt/${pkgname}

	ln -s /opt/${pkgname}/chrome ${pkgdir}/usr/bin/dartium
}
