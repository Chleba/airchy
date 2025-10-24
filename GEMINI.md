# Project: Omarchy - Arch Linux Configuration

## Directory Overview

This directory, "Omarchy," contains a collection of scripts, configuration files, and assets to transform a standard Arch Linux installation into a complete, opinionated web development environment centered around the Hyprland window manager. It automates the setup of a wide range of tools, from system-level utilities to application-specific themes.

## Project Type

This is a **System Configuration Project**. It is not a traditional software project with a build/compile cycle. Instead, it is a set of shell scripts and configuration files that provision and customize a Linux system.

## Key Directories and Files

*   `README.md`: The primary documentation, providing a high-level overview of the project's purpose.
*   `install.sh`: The main entry point for the installation process. It sources scripts from the `install/` directory to perform a step-by-step setup.
*   `bin/`: Contains a large number of `omarchy-*` scripts. These are the primary interface for managing the Omarchy environment, handling tasks like updates (`omarchy-update`), theming (`omarchy-theme-set`), and application launching (`omarchy-launch-browser`). These scripts are intended to be in the user's `$PATH`.
*   `config/`: Holds configuration files for various applications and the system itself. This includes settings for `hypr` (Hyprland), `waybar`, `alacritty`, `starship`, and many others.
*   `install/`: This directory breaks down the installation process into logical units:
    *   `omarchy-base.packages`: A list of essential packages to be installed via `pacman` and `yay`.
    *   `helpers/`, `preflight/`, `packaging/`, `config/`, `login/`, `post-install/`: Subdirectories containing scripts that are executed in sequence by the main `install.sh` script.
*   `themes/`: Contains different visual themes for the Omarchy environment, likely affecting the wallpaper, terminal colors, and UI elements.
*   `default/`: Seems to contain default or fallback configuration files.

## Usage and Development Conventions

*   **Installation:** The primary use is to run the `install.sh` script on a fresh Arch Linux system.
*   **Management:** The system is managed through the various `omarchy-*` scripts located in the `bin/` directory. These scripts appear to be designed as modular, single-purpose commands.
*   **Conventions:**
    *   The project is heavily reliant on shell scripting (`bash`).
    *   Scripts are organized into a modular structure, with a clear separation of concerns (e.g., installation steps, command-line utilities).
    *   Configuration is managed by keeping files in this repository and presumably symlinking them to the correct locations in the user's home directory (e.g., `~/.config`).
