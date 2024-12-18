# Basic Commands for Linux (Arch)

## 📂 **File and Directory Management**

- `ls` – List files and directories.  
  ```bash
  ls -la  # List with details and hidden files
  ```
  `-l` - Long items properties display.
  `-a` - Show hidden files(., ..)
  `-la` - The 2 previous commands merged.
- `cd` – Change directory.  
  ```bash
  cd /desired/path
  ```
- `pwd` – Show the current directory path.
- `mkdir` – Create a new directory.  
  ```bash
  mkdir new_directory
  ```
- `rm` – Delete files or directories.  
  ```bash
  rm file.txt         # Deletes a file
  rm -r directory     # Deletes a directory and its content
  ```
- `cp` – Copy files or directories.  
  ```bash
  cp file.txt /destination/path
  ```
- `mv` – Move or rename files.  
  ```bash
  mv file.txt new_name.txt
  ```

## 🔧 **System Management**

- `pacman` – Arch Linux package manager.  
  ```bash
  sudo pacman -S package           # Install a package
  sudo pacman -R package           # Remove a package
  sudo pacman -Syu                 # Update the system
  sudo pacman -Qs keyword          # Search installed packages
  ```
- `systemctl` – Service and daemon management.  
  ```bash
  sudo systemctl start service     # Start a service
  sudo systemctl stop service      # Stop a service
  sudo systemctl enable service    # Enable a service at startup
  sudo systemctl status service    # Check the status of a service
  ```
- `htop` – Interactive process monitor.  
  ```bash
  sudo pacman -S htop && htop
  ```
- Note: If you want to enable or manage a service with systemd only locally(User only), you need to run one or more of this commands:
  ```bash
  systemctl --user start service # Start a service
  systemctl --user stop service # Stop a service
  systemctl --user enable service # Enable a service at startup
  systemctl --user status sevice # Check the status of a service
  ```
- Syntaxis of systemctl command:
  ```bash
  systemctl --option [command] [service]
  ```
  If it is globally
  ```bash
  sudo systemctl --option [command] [service]
  ```

## 📜 **File Viewing and Editing**

- `cat` – Show the content of a file.  
  ```bash
  cat file.txt
  ```
- `less` – View long files.  
  ```bash
  less file.txt
  ```
- `nano` or `vim` – Text editors.  
  ```bash
  nano file.txt
  ```
- Note: If the file is in a high-rights level
  ```bash
  sudo [program] <file>
  ```
  Example:
  ```bash
  sudo vim /etc/conf.d/sensord
  ```
## 📊 **Disk and Space Management**

- `df` – View filesystem usage.  
  ```bash
  df -h
  ```
- `du` – Check disk usage of a directory or file.  
  ```bash
  du -sh directory
  ```
- `lsblk` – View partitions and block devices.  
  ```bash
  lsblk
  ```

## 🌐 **Internet Connection**
- Connecting to internet
  For Ethernet `dhcpcd` daemon will stablish the connection.
  For WiFi, you can use
  `iwd` package
  or `networkmanager` package
  - Who can be installed with `sudo pacman -S iwd` or `sudo pacman -S networkmanager`
  - And activated with systemd(systemctl) 
- `ping` – Test connectivity to an address.  
  ```bash
  ping -c 4 google.com
  ```
- `ip` – Configure and display network information.  
  ```bash
  ip a
  ```

## 🔑 **Permissions and Ownership**

- `chmod` – Change file permissions.  
  ```bash
  chmod 755 file.sh
  ```
- `chown` – Change the owner of a file.  
  ```bash
  sudo chown user:group file.txt
  ```

## 📦 **Compression and Decompression**

- `tar` – Create or extract tar files.  
  ```bash
  tar -czvf file.tar.gz directory
  tar -xzvf file.tar.gz
  ```
- `zip`/`unzip` – Compress or decompress zip files.  
  ```bash
  zip -r file.zip directory
  unzip file.zip
  ```
- Note: `zip`/`unzip` packages must be installed before running `zip`/`unzip`, you can install them with the following command: `sudo pacman -S zip unzip`.

## 🚀 **Useful Shortcuts**

- `Ctrl + C` – Interrupt a running command.
- `Ctrl + Z` – Suspend a process.
- `Ctrl + R` – Search commands in history.
- `!!` – Execute the last command.  
  ```bash
  sudo !!
  ```
## Recommended packages
- Xscreensaver: `sudo pacman -S xscreensaver` Screensaver
- Conky: `sudo pacman -S conky` Desktop Widgets
- bpytop: `sudo pacman -S bpytop` Better htop
