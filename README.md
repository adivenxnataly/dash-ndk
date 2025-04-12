### Dash for Android NDK
**Dash NDK** is a Dash compiled for Android, this is port from Debian `Linux-based` Dash.

#### What is Dash?
**Dash** (Debian Almquist shell) is a modern POSIX-compliant implementation of `/bin/sh` (sh, Bourne shell). <br>
this is not Bash compatible, but Bash tries to be mostly compatible with POSIX, and thus Dash.

Dash shines in:
- Speed of execution. Roughly 4x times faster than Bash and others.
- Very limited resources (disk space, RAM or CPU).
  > As minimalistic as possible - much smaller (134.1 kB vs 6.5 MB installed, 13 kSLOC vs 176 kSLOC) than Bash and others.
- Security. Dash is a long-established, tiny project with simple and long-established functionality; one that is still very much alive, and with many active developers. Thus, Dash has a much smaller attack surface, while still having many eyes on its code.
- If classic `/bin/sh` needed only.

### How to use?
Download static binaries in [Release Pages](https://github.com/adivenxnataly/dash-ndk/releases) replace manually in `system/bin` according to ur ABI: <br>
`arm64v-8a/armeabi-v7a` <br>
>[!NOTE]
> if ur devices using different ABI likes x86/RISC-V u cant use this.

then, open termux and type `su -c dash` or `su` then type `dash`: <br> <br>
![](https://github.com/adivenxnataly/dash-ndk/blob/main/files/dash-termux-cli.jpg)

### Performance
the explanation at the beginning is just words, so how does it perform in real use-case?

- dash
- bash `termux-based`
- sh `default`

this is benchmark for Shell speed test by looping open-close 1000 times, then see which one is faster:
```shell
#!/system/bin/dash <-- /bin/bash for bash, /system/bin/sh for sh
for i in $(seq 1 1000);
do dash -c ":" ;
done
```

- **dash**: `2.28s` <br><br>
  ![](https://github.com/adivenxnataly/dash-ndk/blob/main/files/dash-speedtest.jpg) <br><br>
- **bash**: `21.01s` <br><br>
  ![](https://github.com/adivenxnataly/dash-ndk/blob/main/files/bash-speedtest.jpg) <br><br>
 - **sh**: `2.80s` <br><br>
  ![](https://github.com/adivenxnataly/dash-ndk/blob/main/files/sh-speedtest.jpg) <br><br>


this proves that dash is very fast and can even compete with Android's built-in sh. <br>
but, I don't recommend using this as a replacement for the default Shell (sh) :
> for example by replacing with: `cp dash /system/bin/sh`

### Source, etc.
**Source**: [Here](https://git.kernel.org/pub/scm/utils/dash/dash.git)
