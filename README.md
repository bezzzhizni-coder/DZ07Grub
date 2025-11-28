# DZ07Grub
> Включить отображение меню Grub.  
> Попасть в систему без пароля несколькими способами.  
> Установить систему с LVM, после чего переименовать VG.  
```
gor@testsrv:~$ sudo !!
sudo awk -F\' '/menuentry / { print $2 }' /boot/grub/grub.cfg
Ubuntu
Ubuntu, with Linux 6.8.0-88-generic
Ubuntu, with Linux 6.8.0-88-generic (recovery mode)
Ubuntu, with Linux 6.8.0-87-generic
Ubuntu, with Linux 6.8.0-87-generic (recovery mode)
UEFI Firmware Settings
> тут пришлось установить гуи
gor@testsrv2:~$ sudo apt install ubuntu-desktop-minimal -y

