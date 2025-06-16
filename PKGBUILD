# Maintainer: hiruocha <hiruocha at gmail dot com>

pkgname=nipaplay-reload-bin
pkgver=1.3.1
pkgrel=1
pkgdesc="一个现代化的跨平台视频播放器"
arch=('x86_64')
url="https://github.com/MCDFsteve/NipaPlay-Reload"
license=('MIT')
depends=('gtk3' 'libpulse' 'alsa-lib' 'mesa' 'mpv')
provides=("${pkgname%-bin}=${pkgver}")
conflicts=("${pkgname%-bin}")
options=('!debug')
source=(
    "${pkgname%-bin}-${pkgver}-${CARCH}.tar.gz::${url}/releases/download/v${pkgver}/NipaPlay-${pkgver}-Linux-amd64.tar.gz"
    "${pkgname%-bin}.png::${url}/raw/main/icon_windows2linux.png"
    "${pkgname%-bin}.desktop"
)
sha256sums=(
    'd3c73d1488a5bcf163799974249809587c362634a123dc50ebcd9415fbafa9f3'
    'de29fa53adecccf8db96197f042793324350650eae62cf2179dc51ab7b665470'
    'c2d36d469bf147500c8ac34ecc871e7e932998023a106a942010d20aa69a4146'
)

package() {
    install -Dm755 "NipaPlay" "${pkgdir}/opt/${pkgname%-bin}/NipaPlay"
    install -Dm755 "run.sh" "${pkgdir}/opt/${pkgname%-bin}/run.sh"

    cp -rp "lib" "${pkgdir}/opt/${pkgname%-bin}/"
    cp -rp "data" "${pkgdir}/opt/${pkgname%-bin}/"

    mkdir -p "${pkgdir}/usr/bin"
    ln -s "/opt/${pkgname%-bin}/run.sh" "${pkgdir}/usr/bin/${pkgname%-bin}"

    install -Dm644 "${srcdir}/${pkgname%-bin}.desktop" "${pkgdir}/usr/share/applications/${pkgname%-bin}.desktop"
    install -Dm644 "${srcdir}/${pkgname%-bin}.png" "${pkgdir}/usr/share/pixmaps/${pkgname%-bin}.png"
}
