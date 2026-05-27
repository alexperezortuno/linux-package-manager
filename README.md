# Linux Package Manager

This script compiles a list of useful commands for Linux distributions, this install, remove, update and upgrade packages and other
things across multiple distributions.

## Supported Distributions

- **Debian/Ubuntu**: Uses `apt` package manager
- **Arch Linux/ArcoLinux**: Uses `pacman` package manager

The script automatically detects your distribution and uses the appropriate package manager.

## Install

```
$ sudo chmod +x install
$ ./install
```

## Running commands

```
$ lpm -h
```

## 🔹 Linux Package Manager (lpm) 🔹
    Automates system updates, upgrades, and cleanup tasks across distributions.

    📌 Usage:
      lpm [OPTION]

    🛠️ Options:
      -h, --help             Show this help message.
      -v, --version          Show script version.

    🔧 System Maintenance
    (no args)   Update, upgrade and clean all

    📚 Available options

    clean       Clean package cache
    cache:stats Show cache statistics

    📦 Package Management
    pkg:install [PACKAGE]      Install a package
    pkg:installed              List installed packages
    pkg:upgrade [PACKAGE]      Upgrade specific package
    pkg:remove [PACKAGE]       Remove a package
    pkg:find [PACKAGE]         Search for a package
    pkg:download [PACKAGE]     Download package
    pkg:dependencies [PACKAGE] Check package dependencies
    pkg:description [PACKAGE]  Show package description
    pkg:descriptions           List all packages with descriptions

    🔄 PPA Management (Debian/Ubuntu only)
    ppa:list          List configured PPAs
    ppa:install <ppa> Add a PPA
    ppa:remove <ppa>  Remove a PPA

    💾 Memory Management
    freemem         Free up memory

    📊 Monitoring
    sys-info        Show system information
    disk-usage      Show disk usage by partition
    memory-info     Show detailed memory usage

    🛡️ Security
    ufw-status       Show UFW status
    ports-list       List open ports and associated services
    check-updates    Check for security updates
    killport <port>  Kill process using a port

    ⚙️ Services
    service-list          List active services
    service-restart <srv> Restart a service

    💡 Tip: Replace [PACKAGE] with package name
