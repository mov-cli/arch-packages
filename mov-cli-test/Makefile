install:
	makepkg -si

uninstall:
	sudo pacman -Rs python-mov-cli-test

clean:
	rm -r ./pkg
	sudo rm -r ./src
	rm ./*.pkg.tar.zst

srcinfo:
	makepkg --printsrcinfo > .SRCINFO