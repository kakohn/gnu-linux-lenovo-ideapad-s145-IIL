# Lenovo-Ideapad-s145-14IIL 
![Captura de pantalla de 2020-09-06 13-09-56](https://user-images.githubusercontent.com/65475712/92333389-4f781900-f042-11ea-82f3-9b1fef047150.png)

# WIFI ✓

### Chip WIFI Realtek rama "rtw88" (rtw_8723de(rtl8723), rtw_8822be(rtl8822be), rtw_8822ce(rtl8822ce))
Dependiendo de la distribución GNU/Linux, instalar la paquetería necesaria para compilar los módulos al kernel.

#### _Debian/Ubuntu_
```
$ sudo apt update && sudo apt upgrade
$ sudo apt install make git-core gcc build-essential linux-headers-$(uname -r)
```
#### _Void Linux_
```
$ sudo xbps-install -Suy
$ sudo xbps-install -S make git-core gcc base-devel linux-headers-$(uname -r)
```
#### _Arch Linux_
```
$ sudo pacman -Suy
$ sudo pacman -S make git-core gcc base-devel linux-headers-$(uname -r)
```
#### _Solus Linux_
```
$ sudo eopkg update
$ sudo eopkg install -c system.devel
$ sudo eopkg install make git-core gcc linux-headers-$(uname -r)
```
#### _Clonar módulo rtw_8822ce rtw_8723de rtw_8822be_ 🔧
```
$ git clone https://github.com/lwfinger/rtw88.git
$ cd rtw88
$ make 
$ sudo make install
$ sudo modprobe <dev_name>
<dev_name> = rtw_8723de 
             rtw_8822be 
             rtw_8822ce 
```
#### _Si el kernel cambiase, compilar de nuevo_

```
$ cd rtw88 
$ make 
$ sudo make install
$ sudo modprobe <dev_name>
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

![Captura de pantalla de 2020-08-18 13-51-39](https://user-images.githubusercontent.com/65475712/90558881-037c3780-e15a-11ea-8039-3ad6a0f2c247.png)

```
GRUB_CMDLINE_LINUX="i8042.nopnp=1 pci=nocrs"
```
_Guardar_ ```ctrl+o``` _y salir_ ```ctrl+x```
```
$ sudo update-grub
$ sudo reboot
```
# Personalización LXDE ✓
![2020-07-06-124157_1366x768_scrot](https://user-images.githubusercontent.com/65475712/86627824-22e24b00-bf86-11ea-9325-eeca4c793d1f.png)

# Personalización Budgie ✓
![Captura de pantalla de 2020-07-30 12-05-22](https://user-images.githubusercontent.com/65475712/89587992-f9744380-d7ff-11ea-838d-96d7102e5f3d.png)

# Compilar Kernel ✓

### _Paquetes necesarios_

#### _Debian/ubuntu_
```
$ sudo apt install build-essential libssl-dev libncurses5-dev gcc bc bison flex libelf-dev
```
#### _Página donde se descarga el código fuente del kernel linux_
https://www.kernel.org/

```
$ mkdir linux
$ cd linux
$ mv ~/Descargas/linux-*.tar.xz ~/linux
$ mkdir linux_kernel
$ tar xvf linux-* -C linux_kernel/ --strip-components=1
$ cd linux_kernel/
$ make localmodconfig   localmodconfig = [Coge solamente el hardware conectado]
$ make deb-pkg
```

# ¡Espero haberte ayudado!
### Grupos de Telegram

#### Windows/GNU/Linux/BSD

https://t.me/KarlasProject

#### Software libre y/o Opensource

https://t.me/drivemeca_opensource
