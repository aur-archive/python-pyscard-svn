# Maintainer: Eric Tellier <newick@fsfe.org>
# Contributor: Jonas Heinrich <onny@project-insanity.org>
# Contributor: Guenther Starnberger <gst@sysfrog.org>
# Contributor:  Artiom Molchanov <ar.molchanov@gmail.com>

pkgname=python-pyscard-svn
pkgver=r669
pkgrel=1
pkgdesc="pyscard is a Python module adding smart cards support to Python"
arch=('i686' 'x86_64')
url="http://pyscard.sourceforge.net/"
license=('LGPL')
depends=('python' 'pcsclite')
makedepends=('swig')
provides=("python-pyscard")
conflicts=("python-pyscard")
source=("python-pyscard::svn+https://svn.code.sf.net/p/pyscard/code/trunk/pyscard")
sha512sums=("SKIP")

pkgver() {
  cd "${srcdir}/python-pyscard"
  local ver="$(svnversion)"
  printf "r%s" "${ver//[[:alpha:]]}"
}

build() {
  cd "${srcdir}/python-pyscard/src"
  python setup.py build_ext
}

package() {
  cd "${srcdir}/python-pyscard/src"
  python setup.py install --prefix="${pkgdir}/usr"
}
