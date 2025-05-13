# Maintainer: hiruocha <hiruocha at gmail dot com>

pkgname=nipaplay-reload-bin
pkgver=1.1.6
pkgrel=1
pkgdesc="一个现代化的跨平台视频播放器"
arch=('x86_64')
url="https://github.com/MCDFsteve/NipaPlay-Reload"
license=('MIT')
depends=('gtk3' 'libpulse' 'alsa-lib' 'mesa')
provides=("${pkgname%-bin}=${pkgver}")
conflicts=("${pkgname%-bin}")
options=('!debug')
source=(
    "${pkgname%-bin}-${pkgver}-${CARCH}.tar.gz::${url}/releases/download/v${pkgver}/NipaPlay-${pkgver}-Linux-amd64.tar.gz"
    "${pkgname%-bin}.png::${url}/raw/main/icon_windows2linux.png"
    "${pkgname%-bin}.desktop"
)
sha256sums=(
    'e2134c3a44a8d58f273c300e59528f893a07b64d7f569b439ea520118c08536e'
    'de29fa53adecccf8db96197f042793324350650eae62cf2179dc51ab7b665470'
    'c2d36d469bf147500c8ac34ecc871e7e932998023a106a942010d20aa69a4146'
)

package() {
    install -Dm755 "NipaPlay" "${pkgdir}/usr/lib/${pkgname%-bin}/NipaPlay"
    install -Dm755 "run.sh" "${pkgdir}/usr/lib/${pkgname%-bin}/run.sh"

    cp -rp "lib" "${pkgdir}/usr/lib/${pkgname%-bin}/"
    cp -rp "data" "${pkgdir}/usr/lib/${pkgname%-bin}/"

    mkdir -p "${pkgdir}/usr/bin"
    ln -s "/usr/lib/${pkgname%-bin}/run.sh" "${pkgdir}/usr/bin/${pkgname%-bin}"

    install -Dm644 "${srcdir}/${pkgname%-bin}.desktop" "${pkgdir}/usr/share/applications/${pkgname%-bin}.desktop"
    install -Dm644 "${srcdir}/${pkgname%-bin}.png" "${pkgdir}/usr/share/pixmaps/${pkgname%-bin}.png"
}