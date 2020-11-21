# Lenovo-Ideapad-s145-14IIL 
![Captura_20_11_13_08-50](https://user-images.githubusercontent.com/65475712/99155250-dae1dc00-267b-11eb-9b7e-07f1a43ac208.png)

# WIFI ✔

### Chip WIFI Realtek rama "rtw88", rtw_8723de(rtl8723de), rtw_8822be(rtl8822be), rtw_8822ce(rtl8822ce).
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
$ sudo make install
$ sudo modprobe <dev_name>
<dev_name> = rtw_8723de 
             rtw_8822be 
             rtw_8822ce 
```

# Touchpad ✔
### Elantech Touchpad

Se debe agregar una linea de GRUB CMD, en el archivo configuración de /etc/default/grub

```
$ sudo nano /etc/default/grub
```
_Agregar una nueva linea de GRUB CMD_

![Captura_20_11_14_13-21](https://user-images.githubusercontent.com/65475712/99155312-56dc2400-267c-11eb-996f-2e10d7c9643d.png)

```
GRUB_CMDLINE_LINUX_DEFAULT="i8042.nopnp=1 pci=nocrs"
```
_Guardar_ ```ctrl+o``` _y salir_ ```ctrl+x```

#### _Debian/Ubuntu/Void Linux_
```
$ sudo update-grub
$ sudo reboot
```
#### _Arch/OpenSUSE_
```
$ grub2-mkconfig -o /boot/grub2/grub.cfg
$ sudo reboot
```
# [Personalización LXDE ✔](https://youtu.be/pzQiQrm0Ei4)
![2020-07-06-124157_1366x768_scrot](https://user-images.githubusercontent.com/65475712/86627824-22e24b00-bf86-11ea-9325-eeca4c793d1f.png)

# [Personalización Budgie ✔](https://youtu.be/jX36ehyIXgQ)
![Captura de pantalla de 2020-07-30 12-05-22](https://user-images.githubusercontent.com/65475712/89587992-f9744380-d7ff-11ea-838d-96d7102e5f3d.png)

# Compilar Kernel ✔

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
$ make localmodconfig               || localmodconfig = [Coge solamente el hardware conectado]
$ make deb-pkg
```

# ¡Espero haberte ayudado!
### Grupos de Telegram

#### Windows/GNU/Linux/BSD ✔

[Karla's Project](https://t.me/KarlasProject)

#### Software libre y/o Opensource ✔

[DriveMeca](https://t.me/drivemeca_opensource)

#### Canal de música Lo-Fi Hip Hop ✔

[low fidelity _-](https://t.me/lowfidelitygg)
