# Adding a new package
To add a new AUR package `<name>`, follow these steps:

- Create directory `src/<name>/`
- In that directory:
  - Create PKGBUILD
  - Run `makepkg --printsrcinfo > .SRCINFO`

# Testing a package

To test if a package is correct, first run `namcap` on its `PKGBUILD` file.
Then, replicate the commands from the script `.tem/path/aurtest` (DO NOT RUN THE SCRIPT ITSELF) in order to run a
container in which you will run the following (some of it is pseudo-code):
```
cd <name>
sudo pacman --noconfirm -S <depends> <optdepends>
makepkg --noconfirm  # DO NOT ADD EXTRA ARGS HERE
```
