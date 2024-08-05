install:
	makepkg -si

uninstall:
	sudo pacman -Rs python-mov-cli-test

clean:
	rm .SRCINFO
	rm -r ./pkg
	sudo rm -r ./src
	rm ./*.pkg.tar.zst

src-info:
	makepkg --printsrcinfo > .SRCINFO