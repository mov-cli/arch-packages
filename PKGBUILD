# Maintainer: Goldy <goldy@devgoldy.xyz>
pkgname=mov-cli
pkgver="4.1.6"
pkgrel=1
pkgdesc="Watch everything from your terminal."
arch=("x86_64" "i686")
url="https://github.com/mov-cli/mov-cli"
license=("MIT")
makedepends=(
	"python-build" "python-setuptools-scm"
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
    python -m installer --destdir="$pkgdir" dist/*.whl
}