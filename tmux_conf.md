# Tmux Config

Tmux conf file is located in "~/.tmux.conf"

### Distro = None

## ~/.tmux.conf

```bash
# Theme
set -g @plugin 'dracula/tmux'

# List of Plugins
set -g @plugin 'tmux-plugins/tpm

# Makes the lines appear thicker
set -g pane-border-lines heavy

# Init TMUX plugin manager
run '~/.tmux/plugins/tpm/tpm'

```
