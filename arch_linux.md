### Arch Linux useful commands
| **Command** | **Description** |
| --------------|-------------------|
| `sudo pacman -Sy archlinux-keyring && sudo pacman -Su` | Upgrade system regularly. |
| `pacman -Qm` | Lists packages not installed from the main repos(ie AUR or pkgbuild). |
| `yay` | Upgrades everything. |
| `yay -Syu --aur` | Upgrades only the aur packages. |
| `makepkg -si` | Compile and install an AUR package. |
| `gcc program-source-code.c -o executable-file-name` | Compile a C program. |
| `g++ program-source-code.cpp -o executable-file-name` | Compile a C++ program. |
| `pacman -Qi <packageName>` | You can then use the exit code to determine if the packages existes on the system or not (0 the package exists, 1 it doesn't) |

 
