# Maintainer: hiruocha <hiruocha at gmail dot com>

pkgname=nipaplay-reload-bin
pkgver=1.3.1
pkgrel=2
pkgdesc="一个现代化的跨平台视频播放器"
arch=('x86_64')
url="https://github.com/MCDFsteve/NipaPlay-Reload"
license=('MIT')
depends=('fuse3' 'desktop-file-utils')
provides=("${pkgname%-bin}=${pkgver}")
conflicts=("${pkgname%-bin}")
options=('!debug' '!strip')
source=(
    "${pkgname%-bin}-${pkgver}-${CARCH}.AppImage::${url}/releases/download/v${pkgver}/NipaPlay-${pkgver}-Linux-amd64.AppImage"
    "${pkgname%-bin}.png::${url}/raw/main/icon_windows2linux.png"
    "${pkgname%-bin}.desktop"
)
sha256sums=(
    '00bfc319a061ecfa7009014e419e2c89e36602552d6cafe5855b39590b67233f'
    'de29fa53adecccf8db96197f042793324350650eae62cf2179dc51ab7b665470'
    'c2d36d469bf147500c8ac34ecc871e7e932998023a106a942010d20aa69a4146'
)

package() {
    install -Dm755 "${pkgname%-bin}-${pkgver}-${CARCH}.AppImage" "${pkgdir}/opt/${pkgname%-bin}/${pkgname%-bin}"

    mkdir -p "${pkgdir}/usr/bin"
    ln -s "/opt/${pkgname%-bin}/${pkgname%-bin}" "${pkgdir}/usr/bin/${pkgname%-bin}"

    install -Dm644 "${srcdir}/${pkgname%-bin}.desktop" "${pkgdir}/usr/share/applications/${pkgname%-bin}.desktop"
    install -Dm644 "${srcdir}/${pkgname%-bin}.png" "${pkgdir}/usr/share/pixmaps/${pkgname%-bin}.png"
}
