### Update Package List and Upgrade System

```bash
sudo apt update && sudo apt upgrade -y
```

### Install cURL

```bash
sudo apt install curl
curl --version
```

### Add custom aliases

```bash
nano ~/.bashrc
```

add this at the end of .bashrc

```bash
if [ -f ~/.bash_aliases ]; then
. ~/.bash_aliases
fi
```

clone .bash_aliases

```bash
cd ~

git clone https://gist.github.com/da49873744fa912665daf87f1cf1b382.git
```

# Optional

### Change User

```jsx
sudo adduser "name"
usermod -aG sudo "name"
su - "name"
```

### Change Host name

Replace any occurence with your new hostname

```bash
sudo nano /etc/hostname
sudo nano /etc/hosts
hostnamectl
sudo reboot
```

### Password

```bash
sudo passwd

# Copy SSH to Server
ssh-copy-id user@server


```bash
# Install Git
	sudo apt-get install git
	git --version
	
	git config --global user.name "augustobritome"
	git config --global user.
	email "augustobrito@outlook.com"
	
	git config --list
	
	# ~/.gitconfig



# Install Dejadup
sudo snap install deja-dup --classic

# Restore folders from backup
projects applicatipns

# Install Fonts
	sudo apt install fonts-firacode
	sudo apt-get install fonts-powerline

# Change Terminal Fonts
gnome-terminal-profile export or import "path/to/profile"


# Install Gnome Tweaks and Extensions
sudo apt install gnome-tweaks
sudo apt install gnome-shell-extensions
sudo apt install chrome-gnome-shell
```

### Remove Bloatwares

```bash

```