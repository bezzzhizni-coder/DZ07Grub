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
```
> тут пришлось установить гуи
```
gor@testsrv2:~$ sudo apt install ubuntu-desktop-minimal -y
```
![Image alt](https://github.com/bezzzhizni-coder/DZ07Grub/blob/5a37328bbd7e2bd6655a83c3a89a72ec4fb4c8e6/46560ab5-9e98-4de5-826a-ea09d6ba8fdc.jpg)
![Image alt](https://github.com/bezzzhizni-coder/DZ07Grub/blob/017e216a28989c38c85e08cf6014e94bebfc3583/4ce72250-6bda-433d-8c80-afb4fc4f6ad6.jpg)
