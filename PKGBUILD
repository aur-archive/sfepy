# Maintainer: Renato Coutinho <renato.coutinho@gmail.com>
pkgname=sfepy
pkgver=2011.3
pkgrel=2
pkgdesc="Simple Finite Elements in Python"
arch=('i686' 'x86_64')
url="http://sfepy.kme.zcu.cz"
license=('BSD')
source=(http://sfepy.googlecode.com/files/${pkgname}-${pkgver}.tar.gz)
md5sums=('3ebf88faabb72295836b22f3e724c90a')

makedepends=('python2-distribute')
depends=('python2-numpy' 'python2-scipy' 'swig' 'python2-pyparsing' 
         'python2-matplotlib' 'python-pytables')

optdepends=('scikits-umfpack: used to solve most systems'
            'python2-sympy: used by some tests and functions'
            'python-pexpect: required by schroedinger.py'
            'gmsh: required by schroedinger.py (2D)'
            'tetgen: required by schroedinger.py (3D)'
            'python2-ipython: required for isfepy'
            'python-multiprocessing: required by log.py (live plotting)')

build() {
   cd ${srcdir}/${pkgname}-${pkgver}
   python2 setup.py build_ext --inplace
   python2 setup.py install --prefix=/usr --root=${pkgdir} || return 1

   cd ${pkgdir}/usr/bin
   mkdir ${pkgdir}/usr/share/${pkgname}/bin
   mv eigen.py findSurf.py genPerMesh.py postproc.py runTests.py shaper.py test_install.py extractor.py friction_slip.py homogen.py plotPerfusionCoefs.py probe.py schroedinger.py simple.py ${pkgdir}/usr/share/${pkgname}/bin
}
