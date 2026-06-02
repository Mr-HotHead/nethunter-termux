# nethunter-termux

**Install Kali NetHunter on your Android phone — no root required.**

Two installation methods are available:

| Method | Script | Managed by | Notes |
|--------|--------|------------|-------|
| **New (recommended)** | `install-kali` | `proot-distro` | Clean, simple, supports backup/restore |
| Legacy | manual steps below | custom proot wrapper | Original workaround method |

---

## Method 1 — proot-distro installer (recommended)

Registers Kali as a native `proot-distro` distribution. No hacky workarounds, no broken packages.

### Prerequisites

- Android phone (no root needed)
- [Termux](https://f-droid.org/packages/com.termux/) from **F-Droid** (not Google Play)

### Steps

```bash
# 1. Update Termux
pkg update && pkg upgrade -y

# 2. Install dependencies
pkg install -y git proot proot-distro tar xz-utils

# 3. Clone this repo
git clone https://github.com/Mr-HotHead/nethunter-termux.git
cd nethunter-termux

# 4. Run the installer (choose one)
bash install-kali --nano       # ~300 MB download, ~950 MB installed
bash install-kali --minimal    # larger, more tools pre-installed
bash install-kali --full       # complete Kali toolset

# 5. Done! Log in:
proot-distro login kali        # as root
nh                             # shortcut
```

### Usage

| Command | Description |
|---------|-------------|
| `proot-distro login kali` | Log in as root |
| `proot-distro login kali --user kali` | Log in as user kali |
| `nh` | Quick login shortcut |
| `nh-root` | Quick root login |
| `nh apt update` | Run a command directly |
| `proot-distro backup kali` | Backup the entire rootfs |
| `proot-distro restore kali` | Restore from backup |
| `proot-distro remove kali` | Uninstall Kali |

### First steps inside Kali

```bash
apt update && apt upgrade -y
apt install -y kali-tools-top10   # or just: apt install nmap
```

### Uninstall

```bash
bash install-kali --remove
# or: proot-distro remove kali
```

---

## Method 2 — Legacy (original manual method)

<details>
<summary>Click to expand legacy instructions</summary>

**Update**: Ignore steps 7,8,9,10 and 11 as the present version installer has OS file with normal rootfs (Incase if you still run into the rootfs error, then follow steps 7, 8 ,9 ,10 and 11 too)

### Pre-Requisites

1. Android Phone (no need to be rooted)
2. Termux App (as you install nethunter in termux only)
3. _Minimum 8GB storage_

### Procedure

1) **Download Termux app** from ~~playstore~~ **F-Droid**
   > Termux app is available only for Android, so you need an Android phone

2) Open Termux and **type** `termux-setup-storage`
   > So termux can access your internal storage

3) Now **type** `pkg install wget`
   > wget tool helps in downloading files from internet in linux environment

4) Now **type** `wget -O install-nethunter-termux https://offs.ec/2MceZWr`
   > The installer is now downloaded

5) Now **type** `chmod 777 install-nethunter-termux`
   > Now you have the permission to run the installer

6) Now **type** `./install-nethunter-termux`
   > The installer is now started

7) Now the installer will download some tools and will *start downloading the Kali-Nethunter OS*, now **click on CTRL+X**, this will _stop the downloading_.
   > The OS downloaded from this installer has its rootfs corrupted, so we stopped the download

8) Now **type** `cd` then `ls`, it will show you two files **kalifs-arm64-full.tar.xz** and **kalifs-arm64-full.tar.xz.st**, remove those files by typing `rm -rf kalifs-arm64-full.tar.xz` and `rm -rf kalifs-arm64-full.tar.xz.st`
   > These files have the corrupted OS, so we don't need them

9) Now **go to** [The OS download page](https://kali.download/nethunter-images/current/rootfs/kalifs-arm64-full.tar.xz), a 1.7GB file will be downloaded
   > This is the Kali-Nethunter OS which doesn't have its rootfs corrupted

10) After the Download is finished, come back to Termux and **go to** the folder where the OS file is downloaded, now **move** the OS file to the home directory by **typing** `mv kalifs-arm64-full.tar.xz /data/data/com.termux/files/home`
    > We need to make sure the installer and the OS file are on same directory

11) Now type `cd` and run the installer by **typing** `./install-nethunter-termux`, it will say ***"Existing rootfs found, delete and download new one (Y/n)?"***, **type** _n_ and click enter.
    > It is asking whether to delete the OS file we downloaded, as we need it to install nethunter we won't delete it.

12) It will show ***"extracting rootfs file"***, that means Kali-Nethunter is being installed.
    > This will take from 30mins-1hour, so make sure you have enough battery in your phone.

13) After the extraction is finished, it will show ***"Delete the existing rootfs file?(Y/n)"***. Type _Y_ if you don't need the OS file as the installation is finished, or type _n_ if you want the OS file for future purposes.

14) Now Kali-Nethunter is successfully installed. Access commands:
    - `nethunter` or `nh` — run CLI version
    - `nethunter -r` — run as root
    - `nethunter kex passwd` — set KeX password
    - `nethunter kex &` — start GUI

15-17) For GUI: install **NetHunter KeX app** from [store.nethunter.com](https://store.nethunter.com), set password with `nethunter kex passwd`, start with `nethunter kex &`, connect via KeX app.

</details>

---

## FAQ

**What is Kali NetHunter?**
> The mobile version of Kali Linux, designed for penetration testing on Android.

**How much storage does it need?**
> Nano: ~1 GB, Minimal: ~3 GB, Full: ~8-10 GB

**Does it have the same tools as desktop Kali?**
> The nano/minimal versions have fewer tools. You can install any tool with `apt install`. Some features requiring kernel access (raw sockets, Wi-Fi monitoring) won't work without root.

---

## License

MIT
