# Informative Starship Theme

A clean and informative Starship prompt configuration for Linux and Termux users.

This theme provides:
- Better prompt readability
- Informative shell sections
- Cleaner command-line appearance
- Modern prompt styling
- Easy installation for beginners

---

# Preview

This theme replaces your current Starship configuration with the provided `informativetheme.toml`.

---

# Requirements

Before installing, make sure you have:

- Python 3 installed
- Starship installed
- Git (optional)
- `rich` Python package installed

---

# Install Dependencies

## Termux

Update packages:

```bash
pkg update && pkg upgrade
```

Install Python:

```bash
pkg install python
```

Install Starship:

```bash
pkg install starship
```

Install the required Python package:

```bash
pip install rich
```

---

# Important Warning

⚠ WARNING:

This installer WILL overwrite your current Starship configuration file:

```bash
~/.config/starship.toml
```

If you already have a custom theme, create a backup first.

---

# Backup Existing Configuration

Recommended:

```bash
mkdir -p ~/.config
cp ~/.config/starship.toml ~/.config/starship-backup.toml
```

Restore later if needed:

```bash
cp ~/.config/starship-backup.toml ~/.config/starship.toml
```

---

# Installation Steps

## Step 1 — Download Theme

Move the theme file somewhere accessible.

Example:

```bash
/storage/emulated/0/Music/informativetheme.toml
```

---

## Step 2 — Create Installer Script

Create file:

```bash
nano install.py
```

Paste this:

```python
#!/usr/bin/env python3

from rich import print
from pathlib import Path
import shutil
import sys

source = Path("/sdcard/Music/informativetheme.toml")
destination = Path.home() / ".config" / "starship.toml"

print("[red][underline]Read Warning:[/][/]")
print("[red]This will overwrite your Starship configuration.[/]")

if input("Proceed? [yes/no]: ").lower() != "yes":
    print("Program exited.")
    sys.exit()

destination.parent.mkdir(parents=True, exist_ok=True)

shutil.copy(source, destination)

print("[green]Theme copied successfully![/]")
```

---

## Step 3 — Make Script Executable

```bash
chmod +x install.py
```

---

## Step 4 — Run Installer

```bash
./install.py
```

OR

```bash
python install.py
```

---

# Enable Starship

Add this line to your shell config.

## Bash

```bash
echo 'eval "$(starship init bash)"' >> ~/.bashrc
```

Reload shell:

```bash
source ~/.bashrc
```

---

## Zsh

```bash
echo 'eval "$(starship init zsh)"' >> ~/.zshrc
```

Reload:

```bash
source ~/.zshrc
```

---

# Common Errors & Fixes

---

## Error:
```bash
ModuleNotFoundError: No module named 'rich'
```

### Fix:

Install Rich:

```bash
pip install rich
```

---

## Error:
```bash
Permission denied
```

### Fix:

Make script executable:

```bash
chmod +x install.py
```

---

## Error:
```bash
starship: command not found
```

### Fix:

Install Starship:

```bash
pkg install starship
```

Verify installation:

```bash
starship --version
```

---

## Error:
```bash
No such file or directory
```

### Cause:
The theme file path is incorrect.

### Fix:

Verify the file exists:

```bash
ls /sdcard/Music/
```

Update the source path inside the script if needed.

---

## Error:
```bash
Storage permission denied
```

### Fix:

Grant storage permission:

```bash
termux-setup-storage
```

Then restart Termux.

---

## Error:
Theme does not appear after installation
```

### Fixes:

Reload shell:

```bash
source ~/.bashrc
```

OR restart Termux completely.

Also verify:

```bash
cat ~/.config/starship.toml
```

---

# Restore Previous Theme

If you created a backup:

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

Remove Starship init line from:

- `~/.bashrc`
- `~/.zshrc`

---

# Notes

- Designed mainly for Termux/Linux
- Compatible with Bash and Zsh
- Python installer is beginner-friendly
- You may freely edit the TOML file later

---

# Credits

- Starship Prompt
- Python
- Rich Library

---

# License

Free to use and modify.
