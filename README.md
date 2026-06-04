# Linux Package Manager (lpm)

Universal package management wrapper for Debian/Ubuntu, Arch Linux, and Fedora/RHEL. One command to update, install, remove, and clean packages across any supported distribution.

## Supported Distributions

| Distribution | Package Manager |
|--------------|-----------------|
| Debian/Ubuntu | `apt` |
| Arch Linux / ArcoLinux | `pacman` |
| Fedora / RHEL / Rocky / Alma | `dnf` |

Script auto-detects your distribution on execution.

## Installation

```bash
sudo chmod +x install
./install
```

Install script adds `lpm` alias to `~/.bashrc`.

## Usage

```bash
lpm [COMMAND] [ARGUMENTS]
```

## Commands

### System Maintenance

| Command | Description |
|---------|-------------|
| `lpm` | Full system update, upgrade, and cache clean |
| `clean` | Remove package cache |
| `cache:stats` | Show cache directory size and package count |
| `fix-broken` | Repair corrupted or broken package installations |
| `kernel:clean` | Remove old kernel packages (keeps current) |
| `repo:check` | Check repository sources for errors |

### Package Management

| Command | Description |
|---------|-------------|
| `pkg:install [PKG]` | Install package from repository |
| `pkg:remove [PKG]` | Remove package and dependencies |
| `pkg:upgrade [PKG]` | Upgrade specific package to latest version |
| `pkg:search [PKG]` | Search for package in repositories |
| `pkg:installed` | List all installed packages |
| `pkg:find [PKG]` | Find installed package by name |
| `pkg:description [PKG]` | Show detailed package information |
| `pkg:descriptions [PKG]` | Search repositories for package descriptions |
| `pkg:dependencies [PKG]` | Show package dependency tree |
| `pkg:download [PKG]` | Download package to cache (no install) |
| `pkg:list` | List all installed packages |

### PPA Management (Debian/Ubuntu only)

| Command | Description |
|---------|-------------|
| `ppa:list` | List configured PPAs |
| `ppa:install <PPA>` | Add a PPA repository |
| `ppa:remove <PPA>` | Remove a PPA repository |

### Memory Management

| Command | Description |
|---------|-------------|
| `freemem` | Clear memory cache and swap, then show usage |
| `memory:info` | Show memory usage (total, used, free) |
| `memory:info full` | Show detailed hardware memory info |

### Monitoring

| Command | Description |
|---------|-------------|
| `sys:info` | Show system info (hostname, OS, kernel, CPU) |
| `disk:usage` | Show disk usage by partition |
| `ports:list` | List open ports and associated services |

### Security

| Command | Description |
|---------|-------------|
| `ufw:status` | Show UFW firewall status and rules |
| `killport <PORT>` | Kill process using specified port |

### Services

| Command | Description |
|---------|-------------|
| `service:list` | List all enabled services |
| `service:restart <SERVICE>` | Restart specified service |

### Persistence

| Command | Description |
|---------|-------------|
| `lpm:status` | Show LPM state (last update, install/update counts) |

### Help

| Command | Description |
|---------|-------------|
| `-h`, `--help` | Show help message |
| `-v`, `--version` | Show script version |

## Quick Examples

```bash
# Update entire system
lpm

# Install a package
lpm pkg:install neofetch

# Remove a package
lpm pkg:remove old-package

# Search for package
lpm pkg:search vim

# Check disk usage
lpm disk:usage

# Free memory
lpm freemem

# View persistence state
lpm lpm:status
```

## Persistence

LPM tracks usage statistics in `~/.lpm/state`:
- Last system update timestamp
- Last cache clean timestamp
- Total packages installed via LPM
- Total system updates via LPM

View state with `lpm lpm:status`.