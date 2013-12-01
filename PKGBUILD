# $Id: PKGBUILD 7017 2009-12-29 20:22:18Z jlichtblau $
# Maintainer: Jaroslav Lichtblau <dragonlord@aur.archlinux.org>
# Contributor: Ronald van Haren <ronald.archlinux.org>
# Contributor: Andreas Wagner <A.Wagner@stud.uni-frankfurt.de>

pkgname=compiz-desktop-git
pkgver=20131107
pkgrel=1
pkgdesc="Compiz standalone metapackage with session files"
arch=('i686' 'x86_64')
url=()
license=('GPL2')
depends=('emerald' 'ccsm' 'compiz-fusion-plugins-main' 'compiz-fusion-plugins-extra' 'compiz-fusion-plugins-unsupported' 'tint2' 'thunar' 'polkit-gnome' 'tumbler' 'thunar-volman' 'thunar-archive-plugin' 'thunar-media-tags-plugin')
makedepends=(git)
optdepends=()
source=()
md5sums=()

_gitroot="git://github.com/empthollow/compiz-desktop-git.git"
_gitname="src"

msg "Connecting to the GIT server...."
    if [[ -d $_gitname ]] ; then
        cd $_gitname
        git pull origin
        msg "The local files are updated..."
    else
        git clone --depth=1 $_gitroot $_gitname 
    fi
    
    msg "GIT checkout done."

build() {
mkdir -p ${pkgdir}/etc/compiz-desktop
mkdir -p ${pkgdir}/usr/share/applications
mkdir -p ${pkgdir}/usr/share/xsessions
mkdir -p ${pkgdir}/usr/bin
cp -p ${srcdir}/boxmenu.desktop ${pkgdir}/usr/share/applications
cp -p ${srcdir}/compiz-session ${pkgdir}/usr/bin
cp -p ${srcdir}/compiz.desktop ${pkgdir}/usr/share/xsessions
cp -p ${srcdir}/menu.xml ${pkgdir}/etc/compiz-desktop
cp -p ${srcdir}/fusion-icon.png ${pkgdir}/etc/compiz-desktop
}
