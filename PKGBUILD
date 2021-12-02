# Maintainer: vascorsd <m+arch@vascorsd.com>

## Adaptation of the install script located at:
# https://github.com/VantaInc/vanta-agent-scripts/blob/de99355c2aac5bc98499bb9827f3d868e153b305/install-linux.sh

pkgname=vanta-cli-debian-bin
pkgver=2.0.3
pkgrel=1
pkgdesc="Vanta security tool for Linux (debian binary)"
arch=('x86_64')
url="https://vanta.com"
license=('custom')
source=("https://vanta-agent-repo.s3.amazonaws.com/targets/versions/${pkgver}/vanta-amd64.deb")
sha256sums=('2d25af250f3ef1656283cf42fcc6c737a052adfeda765d266b034d21226e3842')
provides=('vanta-agent')
conflicts=('vanta-agent')


package() {
  cd "${pkgdir}"
  tar xf "${srcdir}/data.tar.gz"

  # remove useless legacy init scripts
  rm -rf "$pkgdir/etc/init.d"
  rm -rf "$pkgdir/etc/init"
} 


post_install() {
cat <<EOF
A systemd service has been added called "vanta.service".

Change the `AGENT_KEY` and `OWNER_EMAIL` as you need at /etc/vanta.conf.

Then enable/start the systemd service.
EOF
}
