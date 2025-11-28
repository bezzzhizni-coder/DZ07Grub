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
![Image alt](https://github.com/bezzzhizni-coder/DZ07Grub/blob/7dc203a012f6088450f0eba93c104dd8f747844e/850442e6-11da-4b27-93c1-11f1b5a96f5e.jpg)
![Image alt](https://github.com/bezzzhizni-coder/DZ07Grub/blob/3d77066f5836289ebb1a09caf9b67d7f6ef44279/5e12173b-5f56-4e21-959f-78965b858949.jpg)
![Image alt](https://github.com/bezzzhizni-coder/DZ07Grub/blob/3d77066f5836289ebb1a09caf9b67d7f6ef44279/fd18ed53-9d00-4f59-a9c7-02f30801a13f.jpg)
```
gor@testsrv2:~$ sudo apt remove ubuntu-desktop-minimal
gor@testsrv2:~$ sudo apt autoremove
```
```
root@testsrv2:/home/gor# vgs
  VG        #PV #LV #SN Attr   VSize   VFree
  ubuntu-vg   1   1   0 wz--n- <14,25g <4,25g
root@testsrv2:/home/gor# vgrename ubuntu-vg ubuntu-pupupu
  Volume group "ubuntu-vg" successfully renamed to "ubuntu-pupupu"
root@testsrv2:/home/gor# lvs
  LV        VG               Attr       LSize  Pool Origin Data%  Meta%  Move Lo                                                                                                                                                             g Cpy%Sync Convert
  ubuntu-lv ubuntu-pupupu -wi-ao---- 10,00g
root@testsrv2:/home/gor# lvrename ubuntu-pupupu ubuntu-lv ubuntu-pupupu
  Renamed "ubuntu-lv" to "ubuntu-pupupu" in volume group "ubuntu-pupupu"
root@testsrv2:/home/gor# lvs
  LV            VG            Attr       LSize  Pool Origin Data%  Meta%  Move L                                                                                                                                                             og Cpy%Sync Convert
  ubuntu-pupupu ubuntu-pupupu -wi-ao---- 10,00g
```
