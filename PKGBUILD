# Maintainer: Goldy <goldy@devgoldy.xyz>
pkgname=mov-cli
pkgver="4.1.6"
pkgrel=1
pkgdesc="Watch everything from your terminal."
arch=("x86_64" "i686")
url="https://github.com/mov-cli/mov-cli"
license=("MIT")
makedepends=(
	"python-build" "python-setuptools-scm" "python-pipx"
)
depends=(
	"python"
	"python-beautifulsoup4"
	"python-httpx"
	"python-toml"
	"python-typer"
	"python-inquirer"
	"python-unidecode"
	"python-deprecation"

	"nano"
	"mpv"
	"fzf"
)
optdepends=(
	"python-lxml: For faster beautifulsoup parser."

	"vlc: Optional media player."
)
checkdepends=()
provides=("mov-cli")
conflicts=("mov-cli-git")
md5sums=("SKIP")
source=(
	"https://github.com/mov-cli/mov-cli/archive/refs/tags/$pkgver.zip"
)

prepare() {
	python -m pip install devgoldyutils --break-system-packages # this is fine as devgoldyutils doesn't ship and will never ship with dependecies.
}

build() {
	cd $srcdir/$pkgname-$pkgver
	python -m build --wheel --no-isolation
}

package() {
    cd $pkgname-$pkgver
	echo "uwu >> $pkgdir"

	PIPX_BIN_DIR="$srcdir/pipx-bin" pipx install dist/*.whl

	mkdir -p $pkgdir/$HOME/.local/bin/
	mkdir -p $pkgdir/$HOME/.local/share/pipx/venvs/$pkgname

	cp $srcdir/pipx-bin/mov-cli $pkgdir/$HOME/.local/bin/mov-cli
	cp -r $srcdir/pipx-home/venvs/$pkgname $pkgdir/$HOME/.local/share/pipx/venvs/$pkgname
}

pre_remove() {
    pipx uninstall mov-cli
}