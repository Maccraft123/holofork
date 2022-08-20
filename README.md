[![Build ISO](https://github.com/theVakhovskeIsTaken/holoiso/actions/workflows/build.yml/badge.svg)](https://github.com/theVakhovskeIsTaken/holoiso/actions/workflows/build.yml)

![obraz](https://user-images.githubusercontent.com/47303937/183311516-2927dd2a-7c5b-4cf3-abbe-3f35e64ec836.png)
# HoloFork
SteamOS 3 (Holo) archiso configuration.
With couple of twists.
Basically HoloISO+.

Differences from HoloISO:
- Two kernel options: Pure mainline and Mainline with couple patches for usability
- Command line install(Gamepad support TODO)
- Systemd-boot used instead of GRUB
- Much much better support for handheld gaming PCs
- More desktop environment options(TODO)
- Ripped out NVidia GPU support

Supported devices:
- [QEMU](QEMU.md), only for testing
- AYANEO NEXT
- Anbernic Win600(might get removed in future due to ugly hacks required)

Installation process:
-
**Prerequistes:**
- 2GB flash drive
- A supported handheld gaming PC


**Installation:**
- Flash the ISO from [releases](https://github.com/bhaiest/holoiso/releases/latest) or [actions](https://nightly.link/theVakhovskeIsTaken/holoiso/workflows/build/3.0/holoiso) for NVIDIA GPUs using [BalenaEtcher](https://www.balena.io/etcher/), [Rufus](https://rufus.ie) with DD mode, or by typing `sudo dd if=SteamOS.iso of=/dev/sd(your flash drive) bs=4M status=progress oflag=sync`
- Boot into ISO
- Run `holoinstall`
- Enter drive node, starting from, for example, `sda` or `nvme0n1` when asked
- Take your favourite hot beverage, and wait 'till it installs :3

Upon booting, you'll be greeted with Steam Deck's OOBE screen, from where you'll connect to your network, and login to your Steam account, from there, you can exit to KDE Plasma seamlessly by choosing *Switch to desktop* in the power menu, [like so](https://www.youtube.com/watch?v=smfwna2iHho).

Screenshots:
-
![Screenshot_20220508_133916](https://user-images.githubusercontent.com/97450182/167292656-1679e007-4701-4a3c-89ee-2104b5eb12cd.png)
![Screenshot_20220508_133737](https://user-images.githubusercontent.com/97450182/167292672-8bc9032d-4a21-4528-ab7e-b9dbc25a0664.png)
![Screenshot_20220508_133746](https://user-images.githubusercontent.com/97450182/167292722-a68806c1-5768-4790-a8e7-108d7c72bb08.png)
![Screenshot_20220508_133822](https://user-images.githubusercontent.com/97450182/167292731-86fed590-0260-4c5e-ac13-05d284b5fd24.png)
![Screenshot_20220508_134038](https://user-images.githubusercontent.com/97450182/167292734-90036b5f-2571-438e-8951-8d731cd4ae93.png)
![Screenshot_20220508_134051](https://user-images.githubusercontent.com/97450182/167292738-a70d266f-814d-4352-8d38-b920ae3f3381.png)


Notes:
-

This configuration includes Valve's pacman.conf repositories, `holoinstall` script and `holoinstall` post-installation binaries.

This configuration builds a *releng-based ISO*, which is the default Arch Linux redistribution flavor.

Building the ISO:
-
Trigger the build by executing:
```
pacman -Sy archiso
git clone https://github.com/Maccraft123/holofork/
sudo mkarchiso -v holoiso
```
Once it ends, your ISO will be available in the `out` folder.

