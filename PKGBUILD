# Maintainer: Xiao-Long Chen <chenxiaolong@cxl.epac.to>
pkgname=ricoh-e823-fix
pkgver=1.0
pkgrel=6
pkgdesc="Fix for the Ricoh e823 card reader used in Lenovo laptops"
arch=('any')
url="https://bugs.launchpad.net/linux/+bug/790754"
license=('GPL')
# A "linux<=version" dependency will be placed here once the problem is fixed in the kernel
depends=('bash')
optdepends=('systemd: systemd support')
source=('e823fix.modprobe.conf'
        'e823fix.pmutils'
        'e823fix.wrapper'
        'e823fix.systemd')
sha512sums=('89460c477b72ebae605c2cdde0bd1b4f7f35120394077dfb716e2a3f920fbf5d958e84c00ee8bd46650e28439cb07fa820a0226c3243049f1ee29abdd011bd76'
            '3a737f6feefb7a03c0a4e917e8647ad9867e8115988a39c04c2c3c9fcc0150a982f3de5162966ef812a0179b7242b5473677f32b7430e5f0acf2c122a269f53b'
            '9f2ac74f8fe68d9d274b300acb2fa6b6993ea8fb75e1268084d41b996bc61300fd5b652b873adef706ab92bb13d38bb7381b9194c8da9c257429b4fb3d86d5fa'
            'f21f9bbae8cb84d8a820eb0cf888b824dc73cdb5d39894c96449d4d4a192ca9dcced1ca5241c4845eeef83e2ebd7ebb30f9643261e74a28e9fb0ca48a7865c4e')

package() {
  cd "${srcdir}"
  install -Dm644 e823fix.modprobe.conf "${pkgdir}/etc/modprobe.d/e823fix.conf"
  install -Dm755 e823fix.pmutils "${pkgdir}/etc/pm/sleep.d/50_e823fix"
  install -Dm644 e823fix.systemd "${pkgdir}/usr/lib/systemd/system/e823fix.service"
  install -Dm755 e823fix.wrapper "${pkgdir}/usr/sbin/e823fix_wrapper"
}

# vim:set ts=2 sw=2 et:
