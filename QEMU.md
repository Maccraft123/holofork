# Using QEMU for testing

While not really working ATM, due to gamescope requiring Vulkan support and vulkan inside qemu isn't really supported(trust me, i tried) it is useful for testing installation

You're gonna need:
- QEMU installed and working
- KVM working
- A qcow2 image
- OVMF installed

This command should get you started:
```
qemu-system-x86_64 -device virtio-vga-gl -display gtk,gl=on -vga none -bios /usr/share/ovmf/x64/OVMF.fd
```

Add `-drive file=path/goes/here,if=virtio` for your drive, `-smp N -cpu host` to make it faster, `-m NG` to increase ram available for VM and `-cdrom path/to/holofork.iso` to make it actually boot from ISO
