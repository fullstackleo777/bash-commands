# 12. **Update or Upgrade OS**

## 1 - Check what Linux OS is installed

* `cat /etc/os-release` - Show distro name and version (works on most systems).
* `hostnamectl` - Display host info; often includes a pretty OS name.
* `uname -r` - Show kernel version.
* `uname -m` - Show machine/CPU architecture.
* `lsb_release -a` - Show LSB distro info (if the tool is installed).

## 2 - Update the OS (within the current release)

**Debian / Ubuntu / Linux Mint**

* `sudo apt update` - Refresh package indexes.
* `sudo apt upgrade -y` - Upgrade installed packages.
* `sudo apt full-upgrade -y` - Upgrade with dependency changes/removals if needed.
* `sudo apt autoremove --purge -y` - Remove unused packages and configs.

**RHEL / CentOS 7**

* `sudo yum update -y` - Apply available updates.
* `sudo reboot` - Reboot if kernel/core libraries were updated.

**RHEL 8+ / CentOS Stream / Fedora**

* `sudo dnf upgrade -y` - Apply available updates.
* `sudo dnf autoremove -y` - Remove no-longer-needed packages.
* `sudo reboot` - Reboot if kernel/core libs updated.

**openSUSE Leap / Tumbleweed / SLES**

* `sudo zypper refresh` - Refresh repositories.
* `sudo zypper update -y` - Apply package updates.
* `sudo zypper patch` - (Alternative) Apply only patches.

**Arch / Manjaro (rolling)**

* `sudo pacman -Syu` - Sync repos and upgrade system packages.

**Alpine**

* `sudo apk update` - Refresh repository indexes.
* `sudo apk upgrade` - Upgrade installed packages.

## 3 - Upgrade the OS to a new release (distribution upgrade)

**Ubuntu**

* `sudo apt install -y update-manager-core` - Ensure release upgrade tool is installed.
* `sudo do-release-upgrade` - Upgrade to the next supported Ubuntu release.

**Debian**

* `grep VERSION_CODENAME /etc/os-release` - Check current release codename.
* `sudo nano /etc/apt/sources.list` - Replace current codename with the next stable codename.
* `sudo apt update` - Refresh package indexes for the new release.
* `sudo apt full-upgrade -y` - Perform the release upgrade.
* `sudo reboot` - Reboot after upgrade.

**Fedora**

* `sudo dnf upgrade --refresh -y` - Make sure you’re fully up to date.
* `sudo dnf system-upgrade download --releasever=<NEXT_RELEASE> -y` - Download new release packages.
* `sudo dnf system-upgrade reboot` - Reboot into the upgrade process.

**RHEL (major version upgrades via Leapp)**

* `sudo dnf install -y leapp-upgrade` - Install the Leapp upgrade utility.
* `sudo leapp preupgrade` - Run pre-upgrade checks; review the report.
* `sudo leapp upgrade` - Execute the major version upgrade.
* `sudo reboot` - Reboot to complete.

**CentOS Stream**

* `sudo dnf upgrade -y` - Keep current Stream branch updated (major “jump” not a simple command; prefer reinstall/migration guide).

**openSUSE**

* `sudo zypper --releasever=<NEW_LEAP_VERSION> dup` - Leap: switch to the specified new release.
* `sudo zypper dup` - Tumbleweed: rolling; `dup` keeps you current.

**SLES**

* `sudo SUSEConnect --list-extensions` - Review registered products/extensions.
* `sudo zypper --releasever=<TARGET> dup` - Perform a distribution upgrade to the target.

**Arch / Manjaro (rolling)**

* `sudo pacman -Syu` - Rolling release: this already brings you to the latest.

**Alpine**

* `sudo nano /etc/apk/repositories` - Point repositories to the new Alpine version.
* `sudo apk update` - Refresh indexes for the new release.
* `sudo apk upgrade -a` - Upgrade all packages to the available versions.
* `sudo reboot` - Reboot after upgrade.
