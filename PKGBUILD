
pkgname=electerm-bin-electron
pkgver=1.25.50
pkgrel=1
pkgdesc="An electron-based SSH/SFTP Connection manager and terminal. Using the system electron"
arch=("any")
url="https://electerm.html5beta.com"
license=("MIT")
depends=(
    "nss"
    "electron18"
)
optdepends=()
_pkgname="electerm"
provides=('electerm')
conflicts=('electerm')
source=(
	"https://github.com/electerm/electerm/releases/download/v${pkgver}/${_pkgname}-${pkgver}-linux-x64.tar.gz"
	"https://raw.githubusercontent.com/electerm/electerm/master/LICENSE"
        "${_pkgname}.desktop"
        "https://github.com/electerm/electerm-resource/raw/master/res/imgs/electerm-round-128x128.png"
        "${_pkgname}"
)

sha256sums=('6984e60963bb52e46ad8f7039aa00ac1'
         '292b7bd4de561f869625c55d8a60b608'
         '4e0fc58c70fa5fa4b1e581dc0fba8b9e' 'a')

package() {
	cd "${srcdir}/${_pkgname}-${pkgver}-linux-x64" || exit 2
    install -Dm644 "${srcdir}/electerm-round-128x128.png" "${pkgdir}/usr/share/pixmaps/${_pkgname}.png"
    install -Dm644 "resources/app.asar" "${pkgdir}/usr/share/${_pkgname}/app.asar"
    cp -r "resources/app.asar.unpacked" "${pkgdir}/usr/share/${_pkgname}/"
    install -Dm755 "${_pkgname}" "${pkgdir}/usr/bin/${_pkgname}"
    install -Dm644 -t "${pkgdir}/usr/share/applications" "${_pkgname}.desktop"
}
