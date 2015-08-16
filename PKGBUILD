# Maintainer: Edoardo Maria Elidoro <edoardo.elidoro@gmail.com>
# Contributor: Jib <jbc.as (AT) free.fr>
# Last update: 01/28/2011

pkgname=gtk-theme-orange
_pkgname=orange-theme
pkgver=1.6.1
pkgrel=2
pkgdesc="Orange theme for Xfce and Mate."
arch=(any)
license=('GPL')
depends=('gtk-engine-murrine>=0.98')
optdepends=('slim-theme-orange: matching theme for slim login manager')
source=(https://launchpad.net/~bisigi/+archive/ppa/+files/orange-theme_1.6.1.maverick.ppa2+nmu1.tar.gz
        orange.patch)
url="http://www.bisigi-project.org"
md5sums=('0d7ce23ea759194670dac7a7fd7026af'
         '7e4c18158b8c1e31211cb8d1f5d2bb7c')

package() {
   cd ${srcdir}/${_pkgname}
   # installer rép. 
   install -d ${pkgdir}/usr/share/{themes,icons,pixmaps/backgrounds/gnome/abstract,gnome-background-properties,emerald/themes,doc/bisigi/orange}
   #GTK theme
   tar -xzf Gtk/orange.tar.gz -C Gtk/
   #Emerald theme
   mkdir Emerald/orange
   tar -xzf Emerald/orange.emerald -C Emerald/orange

   patch -Np0 <${srcdir}/orange.patch
   cp -R Gtk/orange/ ${pkgdir}/usr/share/themes/
   install -D -m644 Wallpaper/orange.jpg ${pkgdir}/usr/share/pixmaps/backgrounds/gnome/abstract
   install -D -m644 Wallpaper/orange-wallpaper.xml ${pkgdir}/usr/share/gnome-background-properties
   cp -R Emerald/orange ${pkgdir}/usr/share/emerald/themes/
   install -D -m644 credits.txt ${pkgdir}/usr/share/doc/bisigi/orange/
}
