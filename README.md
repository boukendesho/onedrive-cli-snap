## onedrive-cli-snap
[![onedrive-cli](https://snapcraft.io/onedrive-cli/badge.svg)](https://snapcraft.io/onedrive-cli)

[Upstream Project Link](https://github.com/abraunegg/onedrive) 

A free Microsoft OneDrive Client which supports OneDrive Personal, OneDrive for Business, OneDrive for Office365 and SharePoint.

Please note that this is `not` an officially maintained package. Use at your own risk.

Only a few features have been tested. If you encounter any issues, please `do not` reporting to the official project. Kindly report them here instead. 

Due to my limited time and knowledge, problems might not receive fixes.

[![Get it from the Snap Store](https://snapcraft.io/static/images/badges/en/snap-store-black.svg)](https://snapcraft.io/onedrive-cli)

## Install

```bash
$ sudo snap install onedrive-cli
```

## Usage

see: [Official Docs](https://github.com/abraunegg/onedrive/blob/master/docs/USAGE.md)

replace `onedrive` with `onedrive-cli`

## Data & Config file location

Due to the packaging with Snap, the default paths are different.

- Default data directory: /home/$Your_User_Name/snap/onedrive-cli/current/OneDrive
- Default config directory: /home/$Your_User_Name/snap/onedrive-cli/current/.config/onedrive

## Enable Service (Running onedrive-cli in 'monitor' mode in background)

[What is Monitor Mode?](https://github.com/abraunegg/onedrive/blob/master/docs/USAGE.md#running-onedrive-in-monitor-mode)

```bash
$ mkdir -p ~/.config/systemd/user/
$ wget https://raw.githubusercontent.com/boukendesho/onedrive-cli-snap/main/onedrive-cli.service -O ~/.config/systemd/user/onedrive-cli.service
$ systemctl --user daemon-reload
$ systemctl --user enable --now onedrive-cli.service
# check service status
$ systemctl --user status onedrive-cli.service
# check service log
$ journalctl --user-unit onedrive-cli.service
