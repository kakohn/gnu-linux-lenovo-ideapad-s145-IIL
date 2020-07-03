# Lenovo-ideapad-s145-llL
Configuración, bug fixes, y demas cosas sobre compatibilidad.

# WIFI Section 

Realtek 8822ce
Dependiendo de la distribución GNU/Linux, instalar la paquetería necesaría para compilar los modulos al kernel

Debian/Ubuntu
$ sudo apt update && sudo apt upgrade

$ sudo apt install make git gcc build-essential linux-headers-$(uname -r)

Clonar modulo rtw_8822ce

$ git clone https://github.com/lwfinger/rtlwifi_new.git -b -rtw88
$ sudo su -

"# cd /home/user/rtlwifi_new

"# make clean

"# make 

"# make clean

"# make install

"# modprobe rtw_8822ce

# Touchpad Section
Elantech Touchpad

$ sudo nano /etc/default/grub

Agregar una nueva linea CMD

GRUB_CMDLINE_LINUX="i8042.nopnp=1 pci=nocrs"

Guardar "(ctrl+o)" y salir "(ctrl+x)"

$ sudo update-grub
$ sudo reboot
