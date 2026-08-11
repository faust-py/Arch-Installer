# Arch-Installer

A single-file, semi-automated Arch Linux install script for AMD systems (Ryzen + Radeon).
Boot the Arch ISO, run the script, answer a few prompts — end up with a minimal,
boot-ready system: pacman tuned, zram configured, and a Wayland or X11 base ready
for you to build on.

Personal script, tailored to my hardware. Read it before running on anything you care about.

## Requirements

- Booted from the [Arch ISO](https://archlinux.org/download/), UEFI mode
- Internet connection
- AMD CPU + GPU (edit the package lists in `package_list()` if not)

## Usage

```bash
./install.sh
```

You'll be asked to:

1. Pick a disk, partition it in `cfdisk` (EFI + Linux), confirm before erasing
2. Choose Wayland or X11
3. Set a hostname, username, and password

When it's done:

```bash
umount -R /mnt
reboot
```

No desktop environment is installed — that part's up to you.

## Notes

- Refuses to run without UEFI or internet; retries flaky network steps 3x
- **This formats disks.** No dry-run — double check your choices at each prompt
- Not resumable: a failed/rerun starts over from partitioning

## License

Personal script, use at your own risk.
