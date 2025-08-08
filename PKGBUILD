# Maintainer: hiruocha <hiruocha at gmail dot com>

pkgname=nipaplay-reload-bin
_pkgname=NipaPlay
pkgver=1.4.24
pkgrel=1
pkgdesc="一个现代化的跨平台视频播放器"
arch=('x86_64')
url="https://github.com/MCDFsteve/NipaPlay-Reload"
license=('MIT')
depends=('fuse3' 'desktop-file-utils')
provides=("${pkgname%-reload-bin}=${pkgver}")
conflicts=("${pkgname%-reload-bin}")
options=('!debug' '!strip')
source=(
    "${pkgname%-reload-bin}-${pkgver}-${CARCH}.AppImage::${url}/releases/download/v${pkgver}/${_pkgname}-${pkgver}-Linux-amd64.AppImage"
    "${pkgname%-reload-bin}.png::${url}/raw/main/icon_windows2linux.png"
    "${pkgname%-reload-bin}.desktop"
)
sha256sums=(
    '36adc8920b92c02fab236260782d1c594d7a08d921ac258f5d0f3a3fef42bb3d'
    'de29fa53adecccf8db96197f042793324350650eae62cf2179dc51ab7b665470'
    'eb3309ee6c481697c3db412f75aa07659e053442c5e0d762c39105592563e99b'
)

package() {
    install -Dm755 "${pkgname%-reload-bin}-${pkgver}-${CARCH}.AppImage" "${pkgdir}/opt/${pkgname%-reload-bin}/${pkgname%-reload-bin}"

    mkdir -p "${pkgdir}/usr/bin"
    ln -s "/opt/${pkgname%-reload-bin}/${pkgname%-reload-bin}" "${pkgdir}/usr/bin/${pkgname%-reload-bin}"

    install -Dm644 "${srcdir}/${pkgname%-reload-bin}.desktop" "${pkgdir}/usr/share/applications/${pkgname%-reload-bin}.desktop"
    install -Dm644 "${srcdir}/${pkgname%-reload-bin}.png" "${pkgdir}/usr/share/pixmaps/${pkgname%-reload-bin}.png"
}
