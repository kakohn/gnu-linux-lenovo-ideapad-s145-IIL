# Lenovo-ideapad-s145-llL 
![alt text](https://raw.githubusercontent.com/kakohn/Lenovo-ideapad-s145-llL/blob/master/desktop.png?raw=true)

# WIFI Section 📋

## Realtek 8822ce
Dependiendo de la distribución GNU/Linux, instalar la paquetería necesaría para compilar los modulos al kernel.

_Debian/Ubuntu_
```
$ sudo apt update && sudo apt upgrade
$ sudo apt install make git gcc build-essential linux-headers-$(uname -r)
```
_Void Linux_
```
$ sudo xbps-install -Suy
$ sudo xbps-install -S make git gcc base-devel linux-headers-$(uname -r)
```
_Arch Linux_
```
$ sudo pacman -Suy
$ sudo pacman -S make git gcc base-devel linux-headers-$(uname -r)
```
_Solus Linux_
```
sudo eopkg update
sudo eopkg install -c system.devel
sudo eopkg install make git gcc
```
_Clonar modulo rtw_8822ce rtw_8723 rtw_8822be_ 🔧
```
$ git clone https://github.com/lwfinger/rtlwifi_new.git -b -rtw88

$ sudo su -

# cd /home/user/rtlwifi_new

# make clean

# make 

# make clean

# make install

# modprobe <dev_name>

<dev_name> = rtw_8723de rtw_8822be rtw_8822ce 
```
# Touchpad Section 📋
## Elantech Touchpad
```
$ sudo nano /etc/default/grub
```
_Agregar una nueva linea CMD_
```
GRUB_CMDLINE_LINUX="i8042.nopnp=1 pci=nocrs"
```
_Guardar_ ```"(ctrl+o)"``` _y salir_ ```"(ctrl+x)"```
```
$ sudo update-grub
$ sudo reboot
```
