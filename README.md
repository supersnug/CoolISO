These are the files and folders used to build the CoolISO CachyOS development environment.

### buildiso

buildiso is used to build CachyOS ISO.

#### Arguments

~~~
$ ./buildiso.sh -h
Usage: buildiso [options]
    -c                 Disable clean work dir
    -r                 Disable building in RAM on systems with more than 23GB RAM
    -w                 Remove build directory (not the ISO) after ISO file is built
    -h                 This help
    -p <profile>       Buildset or profile [default: desktop]
    -v                 Verbose output to log file, show profile detail (-q)
~~~

* Uses the same signature that normal repo and has no mirrors package to install.

```bash
sudo pacman -Syy
```

### Install necessary packages:
```bash
sudo pacman -S archiso mkinitcpio-archiso git squashfs-tools grub --needed
```

### Clone:
```bash
git clone https://github.com/supersnug/CoolISO.git
cd CoolISO
```

### Build
```bash
sudo ./buildiso.sh -p desktop -v -w
```

As the result iso appears at the `out` folder

The build installs signed CoolOS packages from
[`supersnug/coolos-repo`](https://github.com/supersnug/coolos-repo). The
repository is configured ahead of CachyOS so CoolOS-owned package versions take
priority.
