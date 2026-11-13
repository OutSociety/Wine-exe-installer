# wine-exe-installer

Instalador aislado de aplicaciones `.exe` de Windows en Linux, con Wine, winetricks, DXVK opcional, extracción de icono original y lanzador en el menú de aplicaciones.

[![Licencia: MIT](https://img.shields.io/badge/Licencia-MIT-yellow.svg)](LICENSE)
[![Versión](https://img.shields.io/badge/versi%C3%B3n-1.1.0-blue.svg)](CHANGELOG.md)

## Características

- Prefijo aislado por aplicación — sin conflictos entre programas.
- Dependencias automáticas con `winetricks` (`corefonts`, `vcrun2019`, `wine-mono`, `wine-gecko`).
- DXVK opcional para apps/juegos con DirectX.
- Detección de arquitectura (`win32`/`win64`) según el `.exe`.
- Icono original extraído del ejecutable (`wrestool` + `icotool`).
- Lanzador `.desktop` funcional en el menú de aplicaciones.
- Logging por instalación en `~/.local/share/wine-apps/logs/`.
- Detección de `ntsync` (kernel 6.14+) para mejor rendimiento.
- Receta del prefijo guardada en `prefix-recipe.txt`.
- Notificaciones de escritorio opcionales.

## Requisitos

- Linux con `wine`, `winetricks`, `icoutils`, `imagemagick`.

```bash
# Debian/Ubuntu
sudo apt install wine winetricks icoutils imagemagick

# Arch
sudo pacman -S wine winetricks icoutils imagemagick

# Fedora
sudo dnf install wine winetricks icoutils ImageMagick

# openSUSE
sudo zypper install wine winetricks icoutils ImageMagick
