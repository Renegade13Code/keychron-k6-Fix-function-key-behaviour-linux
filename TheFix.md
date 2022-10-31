# The Fix:
This is a fix for the keychron k6 function keys. The problem that occurs is that both the `Fn1` and `Fn2` keys activate either the media keys or the functionkeys (f1 - f12).

1) Edit or create the file `/etc/modprobe.d/hid_apple.conf`, e.g.:
```
        gksudo gedit /etc/modprobe.d/hid_apple.conf
```
2) Add this line to the previously open file.
```
        options hid_apple fnmode=2
```
3) Save the file and execute the following command to notify hid_apple module to reload it's configuration.

For debian based distros:
```
        sudo update-initramfs -u
```
For fedora:
```
        sudo dracut --regenerate-all --force

```
For arch based:
```
        sudo mkinitcpio -P
```
4) Reboot


