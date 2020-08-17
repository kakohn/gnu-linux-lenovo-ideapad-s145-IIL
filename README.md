# Lenovo-Ideapad-s145-14IIL 
![Captura de pantalla de 2020-08-17 12-00-52](https://user-images.githubusercontent.com/65475712/90428533-5fbf5880-e081-11ea-94fb-0bd29b9d0e8c.png)

# WIFI ✓

### Chip WIFI Realtek rama "rtw88" (rtw_8723de, rtw_8822be, rtw_8822ce)
Dependiendo de la distribución GNU/Linux, instalar la paquetería necesaría para compilar los modulos al kernel.

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

![Captura de pantalla de 2020-08-06 16-17-10](https://user-images.githubusercontent.com/65475712/89588173-5c65da80-d800-11ea-9aff-f43e77949b24.png)

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

# Personalización Budgie
![Captura de pantalla de 2020-07-30 12-05-22](https://user-images.githubusercontent.com/65475712/89587992-f9744380-d7ff-11ea-838d-96d7102e5f3d.png)

# Compilar Kernel

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
```
#### _Mover el linux-*.tar.xz a la carpeta linux_
```
$ mkdir linux_kernel
$ tar xvf linux-* -C linux_kernel/ --strip-components=1
$ cd ./linux_kernel/
$ make localmodconfig   localmodconfig = [Coge solamente el hardware conectado]
$ make deb-pkg
```

# ¡Espero haberte ayudado!
### Grupos de Telegram

#### Windows/GNU/Linux/BSD

https://t.me/KarlasProject

#### Software libre y/o Opensource

https://t.me/drivemeca_opensource
