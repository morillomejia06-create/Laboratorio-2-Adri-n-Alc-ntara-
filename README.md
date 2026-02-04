# ==============================
# PRACTICA 1 – REPOSITORIOS Y PAQUETES
# ==============================

# Actualizar repositorios
sudo apt update

# Actualizar el sistema
sudo apt upgrade -y

# Ver repositorios configurados
cat /etc/apt/sources.list
ls /etc/apt/sources.list.d/

# Buscar bashtop en los repositorios
apt search bashtop

# Instalar snapd (si no está instalado)
sudo apt install snapd -y

# Instalar Bashtop Resource Monitor
sudo snap install bashtop

# Ejecutar bashtop
bashtop

# Desinstalar bashtop
sudo snap remove bashtop

# Eliminar dependencias no utilizadas
sudo apt autoremove -y
sudo apt autoclean


# ==============================
# PRACTICA 2 – CRON Y AT
# ==============================

# Editar tareas cron del usuario
crontab -e

# (Dentro del crontab agregar)
# Actualizar el sistema todos los días a las 11:00 p.m.
0 23 * * * sudo apt update && sudo apt upgrade -y

# Reiniciar el sistema todos los domingos a las 3:00 a.m.
0 3 * * 0 /sbin/reboot

# Ver contenido de /tmp antes
ls /tmp

# Programar eliminación de /tmp en 1 minuto con at
echo "rm -rf /tmp/*" | at now + 1 minute

# Ver tareas programadas con at
atq

# Ver contenido de /tmp después
ls /tmp


# ==============================
# PRACTICA 3 – DISCOS Y MONTAJE
# ==============================

# Ver discos conectados
lsblk

# Crear partición en el nuevo disco
sudo fdisk /dev/sdb

# Formatear la partición en ext4
sudo mkfs.ext4 /dev/sdb1

# Crear carpeta en el Escritorio
mkdir ~/Escritorio/disco20GB

# Montar el disco en el Escritorio
sudo mount /dev/sdb1 ~/Escritorio/disco20GB

# Entrar al directorio montado
cd ~/Escritorio/disco20GB

# Crear archivo solicitado
touch AdrianAlcantara.txt

# Salir del directorio
cd ~

# Desmontar el disco
sudo umount /dev/sdb1

# Montar el disco en /mnt
sudo mount /dev/sdb1 /mnt

# Entrar a /mnt
cd /mnt

# Verificar que el archivo sigue existiendo
ls

