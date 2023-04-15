# snd_soc_acp6x_mach_lenovo_21HY

This thing [patches `snd_soc_acp6x_mach`](https://www.spinics.net/lists/alsa-devel/msg156915.html)
for the _ThinkBook 14 G5+ ARP_, or _ThinkBook 14+_, or _Lenovo 21HY_. It fixes
the internal microphone and make it show up.

New hardware, how fun is it. Absolutely wonderful.

## Installation

Do these everytime kernel updates.

1. Clone this at `/usr/src/snd_soc_acp6x_mach-0.1/`
2. Run this command. Note that **it will error** because I suppose the module
   doesn't have a version _(what the actual f)_. Ignore the error.

```sh
sudo dkms install snd_soc_acp6x_mach/0.1
```

3. Run this command, but replace `<kernel-ver>` with the kernel version. Just
   use the Tab button to autocomplete.

```sh
sudo cp /var/lib/dkms/snd_soc_acp6x_mach/0.1/build/snd-soc-acp6x-mach.ko /lib/modules/<kernel-ver>/kernel/sound/soc/amd/yc/snd-soc-acp6x-mach.ko
```

4. This command has something to do with the kernel module list (I suppose). Run it just for sure.

```sh
update-initramfs -c -k all
```

5. Restart. Done. Microphone should work now.
