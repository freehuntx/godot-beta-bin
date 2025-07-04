pkgname=godot-beta-bin
pkgver=4.5beta1
pkgrel=1
pkgdesc="Godot Engine Beta - Prebuilt binary from GitHub"
arch=('x86_64')
url="https://godotengine.org"
license=('MIT')
depends=('glibc')
source=("https://github.com/godotengine/godot-builds/releases/download/4.5-beta1/Godot_v4.5-beta1_linux.x86_64.zip"
        "godot-beta.desktop")
sha256sums=('SKIP'
            'SKIP')  # You can replace SKIP with the real checksum if you want

package() {
    install -dm755 "$pkgdir/opt/godot-beta"
    bsdtar -xf Godot_v4.5-beta1_linux.x86_64.zip -C "$pkgdir/opt/godot-beta"
    
    # Symlink to /usr/bin for convenience
    install -dm755 "$pkgdir/usr/bin"
    ln -s /opt/godot-beta/Godot_v4.5-beta1_linux.x86_64 "$pkgdir/usr/bin/godot-beta"

    # Install desktop entry
    install -Dm644 "$srcdir/godot-beta.desktop" "$pkgdir/usr/share/applications/godot-beta.desktop"
}
