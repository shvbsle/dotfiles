# dotfiles

Personal development environment configuration for terminal-based workflow with Neovim, Tmux, Fish shell, and Alacritty.

## 🚀 Quick Start

Bootstrap dotfiles on a new system:

```sh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/shvbsle/dotfiles/main/.local/bin/dot)"
```

After installation, use the `dot` command to manage your dotfiles:
```sh
dot status          # Check dotfiles status
dot add <file>      # Add new dotfile
dot commit -m "msg" # Commit changes
dot push            # Push to remote
```

## 📦 What's Included

- **Neovim** - LSP-powered editor with 10+ plugins (Treesitter, Telescope, nvim-cmp, etc.)
- **Tmux** - Terminal multiplexer with Vim-like navigation
- **Fish** - Modern shell with abbreviations and custom functions
- **Alacritty** - GPU-accelerated terminal emulator
- **Git** - Configuration with useful aliases
- Utility scripts: `vipe`, `xenv`

### Supported Languages
C, C++, Go, Lua, Python, Rust, TypeScript, TOML, JSON

### Prerequisites
- **Required:** Git, Curl
- **Recommended:** Fish shell, Tmux, Neovim 0.10+, Alacritty
- **Optional:** eza, yazi, kubectl, cargo, go

---

## 📝 Cheatsheet

### Tmux Key Bindings

**Prefix:** `Ctrl-A` (all commands below require prefix first)

#### Sessions & Windows
| Key | Action |
|-----|--------|
| `Ctrl-Space` | Switch to last window |
| `Ctrl-H` | Previous window |
| `Ctrl-L` | Next window |
| `c` | Create new window |
| `d` | Detach from session |
| `$` | Rename session |
| `,` | Rename window |

#### Pane Management
| Key | Action |
|-----|--------|
| `-` | Split pane vertically |
| `\` | Split pane horizontally |
| `h/j/k/l` | Navigate panes (Vim-style) |
| `H/J/K/L` | Resize panes (Vim-style) |
| `Ctrl-H/J/K/L` | Swap panes in direction |
| `x` | Kill current pane |
| `z` | Toggle pane zoom |
| `Space` | Cycle through layouts |

#### Copy Mode
| Key | Action |
|-----|--------|
| `[` | Enter copy mode |
| `v` | Begin selection (in copy mode) |
| `y` | Copy selection (in copy mode) |
| `]` | Paste buffer |

---

### Neovim Key Bindings

**Leader:** `Space`

#### File Operations
| Key | Action |
|-----|--------|
| `<leader>w` | Write file |
| `<leader>q` | Quit |
| `<leader>e` | Toggle file explorer |
| `Ctrl-P` | Find files (Telescope) |
| `<leader>sf` | Search files |
| `<leader>sg` | Search by grep |
| `<leader>sb` | Search buffers |
| `<leader>sh` | Search help |

#### LSP & Code Navigation
| Key | Action |
|-----|--------|
| `gd` | Go to definition |
| `gr` | Go to references |
| `gI` | Go to implementation |
| `<leader>D` | Type definition |
| `<leader>ds` | Document symbols |
| `<leader>ws` | Workspace symbols |
| `<leader>rn` | Rename symbol |
| `K` | Hover documentation |
| `F` | Format code |
| `<leader>ca` | Code action |

#### Diagnostics
| Key | Action |
|-----|--------|
| `<leader>dd` | Show diagnostics (Telescope) |
| `<leader>dl` | Show line diagnostics |
| `<leader>dn` | Next diagnostic |
| `<leader>dp` | Previous diagnostic |
| `<leader>df` | Float diagnostic message |

#### Window Management
| Key | Action |
|-----|--------|
| `Ctrl-H/J/K/L` | Navigate windows (Vim-style) |
| `<leader>wv` | Split window vertically |
| `<leader>ws` | Split window horizontally |
| `<leader>wc` | Close window |

#### Autocompletion (Insert Mode)
| Key | Action |
|-----|--------|
| `Ctrl-N` | Next suggestion |
| `Ctrl-P` | Previous suggestion |
| `Ctrl-Y` | Confirm selection |
| `Ctrl-E` | Cancel completion |
| `Ctrl-Space` | Trigger completion |
| `Ctrl-L` | Next snippet field |
| `Ctrl-H` | Previous snippet field |

---

### Fish Shell Abbreviations

Type these abbreviations and press Space to expand:

| Abbreviation | Expands to | Description |
|--------------|------------|-------------|
| `g` | `git` | Git command |
| `t` | `tmux` | Tmux command |
| `c` | `cargo` | Rust cargo |
| `k` | `kubectl` | Kubernetesctl |
| `vi`, `vim` | `nvim` | Neovim editor |
| `ls` | `eza` or `ls` | List files (uses eza if available) |
| `ll` | `eza -l` or `ls -lh` | List with details |
| `lll` | `eza -la` or `ls -lah` | List all with details |

#### Custom Functions
- `yy` - Launch Yazi file manager (changes directory on exit)

---

### Git Aliases

Configured in [.gitconfig](.gitconfig):

| Alias | Command | Description |
|-------|---------|-------------|
| `git c` | `commit` | Commit changes |
| `git s` | `status` | Show status |
| `git lg` | `log --oneline` | Compact log view |
| `git ss` | `stash list` | Search stashes |
| `git sa` | `stash apply` | Apply stash |

---

### Utility Scripts

Located in [.local/bin/](.local/bin/):

- **`dot`** - Manage dotfiles (wrapper for git)
- **`vipe`** - Edit pipe data in editor: `echo "text" | vipe | command`
- **`xenv`** - Source env file and run command: `xenv .env python app.py`

---

## 🎨 Theme & Appearance

- **Neovim:** Catppuccin (transparent background)
- **Terminal:** Alacritty with 80% opacity
- **Font:** JetBrainsMono Nerd Font
- **Tmux Status:** Top-positioned with custom colors

## ⚡ Performance Features

- **CPU-aware plugin loading** - Disables expensive UI features (Noice) on slow systems
- **Format on save** - Automatic code formatting via LSP
- **Lazy loading** - Plugins load on-demand for faster startup
- **Optimized Treesitter** - Smart incremental selection and syntax highlighting

## 📚 Resources

- [Neovim init.lua](.config/nvim/init.lua) - Full editor configuration
- [Tmux config](.tmux.conf) - Terminal multiplexer setup
- [Fish config](.config/fish/conf.d/config.fish) - Shell configuration
- [Alacritty config](.config/alacritty/alacritty.toml) - Terminal emulator settings

## 🔧 Customization

To modify configurations:

```sh
# Edit Neovim config
nvim ~/.config/nvim/init.lua

# Edit Tmux config
nvim ~/.tmux.conf

# Edit Fish config
nvim ~/.config/fish/conf.d/config.fish

# Reload Tmux config
tmux source ~/.tmux.conf
```

---

**Tip:** Keep this README handy as a quick reference for key bindings and commands!
