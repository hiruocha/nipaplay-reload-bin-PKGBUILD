# Maintainer: hiruocha <hiruocha at gmail dot com>

pkgname=nipaplay-reload-bin
_pkgname=NipaPlay
_desktop_name=io.github.MCDFsteve.NipaPlay-Reload
pkgver=1.4.33
pkgrel=1
pkgdesc="一个现代化的跨平台视频播放器"
arch=('x86_64')
url="https://github.com/MCDFsteve/NipaPlay-Reload"
license=('MIT')
depends=('mpv' 'gtk3' 'ffmpeg' 'libass' 'libkeybinder3')
provides=("${pkgname%-reload-bin}=${pkgver}")
conflicts=("${pkgname%-reload-bin}")
options=('!debug')
source=(
    "${pkgname%-reload-bin}-${pkgver}-${CARCH}.tar.gz::${url}/releases/download/v${pkgver}/${_pkgname}-${pkgver}-Linux-amd64.tar.gz"
    "${_desktop_name}.png::${url}/raw/main/assets/icons/flatpak/hicolor/512x512/apps/io.github.MCDFSteve.NipaPlay-Reload.png"
    "${_desktop_name}.desktop::${url}/raw/main/assets/linux/${_desktop_name}.desktop"
)
sha256sums=('12843f12709913a000d4e6858156c2f39b40d86c2ce6a57b348d59ac8e43a11d'
            '77e3890478c5c687e9f4531884d34062aa8f0b7aedaf7f562a2c4d3fb776ffda'
            'd032abed9d298e87825e842b2181a9379292acefae775e9bd2840f264eaba16f')

package() {
    install -Dm755 "NipaPlay" "${pkgdir}/opt/${pkgname%-reload-bin}/NipaPlay"

    cp -rp "lib" "${pkgdir}/opt/${pkgname%-reload-bin}/"
    cp -rp "data" "${pkgdir}/opt/${pkgname%-reload-bin}/"

    install -Dm644 "${srcdir}/${_desktop_name}.desktop" "${pkgdir}/usr/share/applications/${_desktop_name}.desktop"
    install -Dm644 "${srcdir}/${_desktop_name}.png" "${pkgdir}/usr/share/icons/hicolor/512x512/apps/${_desktop_name}.png"
}
