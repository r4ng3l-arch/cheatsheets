### Arch Linux Useful Commands

| **Command** | **Description** |
|--------------|-------------------|
| `sudo pacman -Sy archlinux-keyring && sudo pacman -Su` | Upgrade system regularly. |
| `pacman -Qm` | Lists packages not installed from the main repos (i.e., AUR or pkgbuild). |
| `paru` | Upgrades everything (official and AUR packages). |
| `paru -Syu --aur` | Upgrades only the AUR packages. |
| `paru -Rns <package-name>` | Remove a specific AUR package along with unused dependencies. |
| `paru -Yc` | Clean up orphaned packages. |
| `makepkg -si` | Compile and install an AUR package. |
| `gcc program-source-code.c -o executable-file-name` | Compile a C program. |
| `g++ program-source-code.cpp -o executable-file-name` | Compile a C++ program. |
| `pacman -Qi <package-name>` | Determine if the package exists on the system or not. |
| `sudo pacman -Rns <package-name>` | Remove a package and its unused dependencies. |
| `sudo pacman -Qtdq` | List orphaned packages. |
| `sudo pacman -Scc` | Remove all cached package files. |
| `sudo pacman -Ss` | Search packages. |
| `sudo pacman -U <package-file>.tar.zst` | Install a local package file. |
| `sudo pacman -F <file>` | Search for a package that provides a specific file. |
| `sudo pacman -D --asdeps <package-name>` | Mark a package as a dependency. |
| `sudo pacman -D --asexplicit <package-name>` | Mark a package as explicitly installed. |
| `paru -G <package-name>` | Download the PKGBUILD of an AUR package. |
