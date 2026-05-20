# Informative Starship Theme

A clean, modern, and informative Starship prompt theme for Linux and Termux users.

This repository provides:
- Informative shell prompt layout
- Clean prompt styling
- Beginner-friendly installer
- Easy theme switching
- Automatic configuration setup

---

# Repository

[github.com](https://reference-url-citation.invalid/0)

---

# Features

- Modern Starship prompt
- Simple installation process
- Works on Termux
- Bash & Zsh support
- Automatic config overwrite
- Lightweight setup

---

# Requirements

Before installation, make sure you have:

- Python 3
- Git
- Starship
- Internet connection

---

# Installation Guide

## Step 1 — Update Packages

For Termux users:

```bash
pkg update && pkg upgrade -y
```

---

## Step 2 — Install Required Packages

```bash
pkg install python git starship -y
```

---

## Step 3 — Grant Storage Permission

Required for accessing files from internal storage.

```bash
termux-setup-storage
```

Restart Termux after granting permission.

---

## Step 4 — Clone Repository

```bash
git clone https://github.com/IYOO-areosI3/Informative-theme.git
```

Enter repository:

```bash
cd Informative-theme
```

---

## Step 5 — Install Python Dependency

```bash
pip install rich
```

---

## Step 6 — Run Installer

```bash
python setup
```
---

# What The Installer Does

The installer will:

- Create `~/.config` if missing
- Copy theme config automatically
- Overwrite existing Starship config
- Install the informative theme

Target config location:

```bash
~/.config/starship.toml
```

---

# Important Warning

⚠ WARNING:

Running the installer WILL overwrite your current Starship configuration.

If you already use a custom theme, create a backup first.

---

# Backup Existing Theme

Create backup:

```bash
cp ~/.config/starship.toml ~/.config/starship-backup.toml
```

Restore backup later:

```bash
cp ~/.config/starship-backup.toml ~/.config/starship.toml
```

---

# Enable Starship

## Bash Users

Add Starship initialization:

```bash
echo 'eval "$(starship init bash)"' >> ~/.bashrc
```

Reload shell:

```bash
source ~/.bashrc
```

---

## Zsh Users

Add initialization:

```bash
echo 'eval "$(starship init zsh)"' >> ~/.zshrc
```

Reload shell:

```bash
source ~/.zshrc
```

---

# Verify Installation

Check Starship version:

```bash
starship --version
```

Check installed config:

```bash
cat ~/.config/starship.toml
```

---

# Common Errors & Fixes

---

## Error:
```bash
ModuleNotFoundError: No module named 'rich'
```

### Fix

Install Rich:

```bash
pip install rich
```

---

## Error:
```bash
Permission denied
```

### Fix

Make installer executable:

```bash
chmod +x install.py
```

---

## Error:
```bash
starship: command not found
```

### Fix

Install Starship:

```bash
pkg install starship
```

Verify:

```bash
starship --version
```

---

## Error:
```bash
git: command not found
```

### Fix

Install Git:

```bash
pkg install git
```

---

## Error:
```bash
fatal: destination path already exists
```

### Fix

Remove old repository:

```bash
rm -rf -Informative-theme
```

Then clone again.

---

## Error:
```bash
Storage permission denied
```

### Fix

Run:

```bash
termux-setup-storage
```

Restart Termux afterward.

---

## Error:
Theme not appearing after install
```

### Fixes

Reload shell:

```bash
source ~/.bashrc
```

OR restart Termux completely.

Verify config exists:

```bash
ls ~/.config/
```

Check contents:

```bash
cat ~/.config/starship.toml
```

---

# Updating Theme

Go into repository:

```bash
cd -Informative-theme
```

Pull latest changes:

```bash
git pull
```

Run installer again:

```bash
python install.py
```

---

# Restore Previous Theme

If backup exists:

```bash
cp ~/.config/starship-backup.toml ~/.config/starship.toml
```

Reload shell:

```bash
source ~/.bashrc
```

---

# Uninstall

Remove Starship config:

```bash
rm ~/.config/starship.toml
```

Remove initialization line from:

- `~/.bashrc`
- `~/.zshrc`

Optionally uninstall Starship:

```bash
pkg remove starship
```

---

# Notes

- Designed mainly for Termux/Linux
- Works best with Nerd Fonts
- Compatible with Bash & Zsh
- Theme is customizable
- Safe for beginners

---

# Credits

- Starship Prompt
- Python
- Rich Library

---

# License

Free to use, modify, and distribute.