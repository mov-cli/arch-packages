# Official Arch Linux packages for mov-cli

- [mov-cli](https://aur.archlinux.org/packages/mov-cli)
- [python-mov-cli-test](https://aur.archlinux.org/packages/python-mov-cli-test)
- [python-mov-cli-youtube](https://aur.archlinux.org/packages/python-mov-cli-youtube)
- [python-mov-cli-files](https://aur.archlinux.org/packages/python-mov-cli-files)
- [python-mov-cli-ms](https://aur.archlinux.org/packages/python-mov-cli-ms)

## How to publish to AUR. *(for future maintainers)*

1. Clone this repo.
```sh
git clone https://github.com/mov-cli/arch-packages
```

2. CD into the package you would like to update / upload to the AUR.
```sh
cd mov-cli-youtube
```
> This is an example.

3. Init the git repo inside there and pull it's changes. *Rebase if it tells you to.*
```sh
make init-repo
git pull
```

4. Make your changes, generate a new .SRCINFO file and then commit that.
```sh
make src-info
git add *
git add .SRCINFO
git commit -m "chore: update package to {version-num}"
```

5. Push you changes to the AUR.
```sh
git push --set-upstream aur master
```