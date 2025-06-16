# Maintainer: hiruocha <hiruocha at gmail dot com>

pkgname=nipaplay-reload-bin
_pkgname=NipaPlay
pkgver=1.3.1
pkgrel=3
pkgdesc="一个现代化的跨平台视频播放器"
arch=('x86_64')
url="https://github.com/MCDFsteve/NipaPlay-Reload"
license=('MIT')
depends=('fuse3' 'desktop-file-utils')
provides=("${pkgname%-reload-bin}=${pkgver}")
conflicts=("${pkgname%-reload-bin}")
options=('!debug' '!strip')
source=(
    "${pkgname%-reload-bin}-${pkgver}-${CARCH}.AppImage::${url}/releases/download/v${pkgver}/${_pkgver}-${pkgver}-Linux-amd64.AppImage"
    "${pkgname%-reload-bin}.png::${url}/raw/main/icon_windows2linux.png"
    "${pkgname%-reload-bin}.desktop"
)
sha256sums=(
    '00bfc319a061ecfa7009014e419e2c89e36602552d6cafe5855b39590b67233f'
    'de29fa53adecccf8db96197f042793324350650eae62cf2179dc51ab7b665470'
    'c2d36d469bf147500c8ac34ecc871e7e932998023a106a942010d20aa69a4146'
)

package() {
    install -Dm755 "${pkgname%-reload-bin}-${pkgver}-${CARCH}.AppImage" "${pkgdir}/opt/${pkgname%-reload-bin}/${pkgname%-reload-bin}"

    mkdir -p "${pkgdir}/usr/bin"
    ln -s "/opt/${pkgname%-reload-bin}/${pkgname%-reload-bin}" "${pkgdir}/usr/bin/${pkgname%-reload-bin}"

    install -Dm644 "${srcdir}/${pkgname%-reload-bin}.desktop" "${pkgdir}/usr/share/applications/${pkgname%-reload-bin}.desktop"
    install -Dm644 "${srcdir}/${pkgname%-reload-bin}.png" "${pkgdir}/usr/share/pixmaps/${pkgname%-reload-bin}.png"
}
