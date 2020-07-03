# Lenovo-ideapad-s145-llL
Configuración, bug fixes, y demas cosas sobre compatibilidad.

# WIFI Section 

## Realtek 8822ce
Dependiendo de la distribución GNU/Linux, instalar la paquetería necesaría para compilar los modulos al kernel.

_Debian/Ubuntu_
```
$ sudo apt update && sudo apt upgrade
$ sudo apt install make git gcc build-essential linux-headers-$(uname -r)
```
_Clonar modulo rtw_8822ce_
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
# Touchpad Section
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
