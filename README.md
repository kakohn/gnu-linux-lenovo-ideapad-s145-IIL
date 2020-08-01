# Lenovo-Ideapad-s145-IIL 
![2020-07-08-074912_1366x768_scrot](https://user-images.githubusercontent.com/65475712/86926662-918ee800-c0ef-11ea-9a47-411b02ce7b33.png)

# WIFI ✓

### Chip WIFI Realtek rama "rtw88" (rtw_8723de, rtw_8822be, rtw_8822ce)
Dependiendo de la distribución GNU/Linux, instalar la paquetería necesaría para compilar los modulos al kernel.

#### _Debian/Ubuntu_
```
$ sudo apt update && sudo apt upgrade
$ sudo apt install make git gcc build-essential linux-headers-$(uname -r)
```
#### _Void Linux_
```
$ sudo xbps-install -Suy
$ sudo xbps-install -S make git gcc base-devel linux-headers-$(uname -r)
```
#### _Arch Linux_
```
$ sudo pacman -Suy
$ sudo pacman -S make git gcc base-devel linux-headers-$(uname -r)
```
#### _Solus Linux_
```
$ sudo eopkg update
$ sudo eopkg install -c system.devel
$ sudo eopkg install make git gcc linux-headers-$(uname -r)
```
#### _Clonar modulo rtw_8822ce rtw_8723de rtw_8822be_ 🔧
```
$ git clone https://github.com/lwfinger/rtw88.git
$ sudo su -
# cd /home/user/rtw88
# make clean
# make 
# make clean
# make install
# modprobe <dev_name>
<dev_name> = rtw_8723de 
             rtw_8822be 
             rtw_8822ce 
```
#### _Si el kernel cambiase, compilar de nuevo_

```
$ sudo su -
# cd /home/user/rtw88
# make clean
# make 
# make clean
# make install
# modprobe <dev_name>
<dev_name> = rtw_8723de 
             rtw_8822be 
             rtw_8822ce 
```

# Touchpad ✓
#### Elantech Touchpad

Se debe agregar una linea de GRUB CMD, en el archivo configuración de /etc/default/grub

```
$ sudo nano /etc/default/grub
```
_Agregar una nueva linea de GRUB CMD_

![2020-07-08-074154_722x470_scrot](https://user-images.githubusercontent.com/65475712/86925810-8ab3a580-c0ee-11ea-9495-9742eed36672.png)
```
GRUB_CMDLINE_LINUX="i8042.nopnp=1 pci=nocrs"
```
_Guardar_ ```ctrl+o``` _y salir_ ```ctrl+x```
```
$ sudo update-grub
$ sudo reboot
```
# Personalización LXDE
![2020-07-06-124157_1366x768_scrot](https://user-images.githubusercontent.com/65475712/86627824-22e24b00-bf86-11ea-9325-eeca4c793d1f.png)

# ¡Espero haberte ayudado!
### Grupos de Telegram
#### Windows/GNU/Linux/BSD
```
https://t.me/KarlasProject
```
#### Software libre y/o Opensource
```
https://t.me/drivemeca_opensource
```
