# Alacritty Config

Alacritty conf file is located in "~/.config/alacritty/alacritty.toml"

### Distro = None

## Dependencies

```zsh
$ sudo apt install -y alacritty 
$ mkdir -p ~/.local/share/fonts
$ wget https://github.com/ryanoasis/nerd-fonts/releases/download/v3.1.1/JetBrainsMono.zip
$ unzip -o JetBrainsMono.zip -d ~/.local/share/fonts
$ rm JetBrainsMono.zip
$ fc-cache -fv
```

## ~/.config/alacritty/alacritty.toml

```toml
# ----------------------------------------------------------------------------
# Window Settings
# ----------------------------------------------------------------------------
[window]
# Adds "breathing room" around your Neovim and Tmux borders.
padding = { x = 8, y = 8 }

# "None" removes the title bar and borders for a strictly minimal look.
# Use "Full" if you want the standard window controls back.
decorations = "None"

# slight transparency (0.95 is safe; lower is more transparent).
opacity = 0.95

# ----------------------------------------------------------------------------
# Font Settings
# ----------------------------------------------------------------------------
[font]
# Requires "JetBrainsMono Nerd Font" installed on your system.
normal = { family = "JetBrainsMono Nerd Font", style = "Regular" }
bold = { family = "JetBrainsMono Nerd Font", style = "Bold" }
italic = { family = "JetBrainsMono Nerd Font", style = "Italic" }
size = 11.5

# ----------------------------------------------------------------------------
# Colors (Theme: Carbon / Default Dark)
# ----------------------------------------------------------------------------
[colors]
primary = { background = "#161616", foreground = "#f2f4f8" }
cursor = { text = "#161616", cursor = "#f2f4f8" }

[colors.normal]
black   = "#161616"
red     = "#ee5396"
green   = "#42be65"
yellow  = "#ffe97b"
blue    = "#33b1ff"
magenta = "#be95ff"
cyan    = "#3ddbd9"
white   = "#dde1e6"

[colors.bright]
black   = "#525252"
red     = "#ff7eb6"
green   = "#6fdc8c"
yellow  = "#fff1a5"
blue    = "#82cfff"
magenta = "#d6bfff"
cyan    = "#85e5e4"
white   = "#f2f4f8"

# ----------------------------------------------------------------------------
# Keybindings (Clipboard Support)
# ----------------------------------------------------------------------------
[keyboard]
# Maps standard Ctrl+Shift+C/V to the system clipboard
bindings = [
  { key = "C", mods = "Control|Shift", action = "Copy" },
  { key = "V", mods = "Control|Shift", action = "Paste" },
  { key = "0", mods = "Control", action = "ResetFontSize" },
  { key = "Equals", mods = "Control", action = "IncreaseFontSize" },
  { key = "Minus", mods = "Control", action = "DecreaseFontSize" },
]
```

## Complexities

Using `alacritty` will mean that the standard shell upgrade will change slightly since the victim will have `no fucking idea` what `alacritty` is.

```bash
# Typical Shell Stabilization Workflow
python3 -c 'import pty; pty.spawn("/bin/bash")'
Ctrl+Z

# In your Alacritty terminal:
stty raw -echo; fg

# Back in the victim shell:
export TERM=xterm-256color   <-- CRITICAL STEP
```
