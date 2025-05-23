
## 🎓 **Curso: Instala tu propio servidor en casa con Linux**

---

### 🧩 Módulo 1 – Introducción al curso✅

* ¿Qué es un servidor y para qué sirve?✅
* ¿Qué puedes hacer con un servidor en casa?✅
* Ejemplos reales: servidor web, servidor de archivos, servidor de medios, nube personal.✅
* Requisitos básicos (PC vieja, laptop, Raspberry Pi, máquina virtual)✅

---

### 🖥️ Módulo 2 – Preparando el entorno✅

* ¿Qué distribución Linux usar? (Ubuntu Server recomendado)✅
* Descargar Ubuntu Server LTS (versión recomendada)✅
* Crear USB booteable con **Rufus o Balena Etcher**✅
* Configurar BIOS para boot desde USB✅

---

### 💽 Módulo 3 – Instalación de Ubuntu Server✅

* Instalación paso a paso (en hardware real o virtual)✅
* Particionado automático o manual✅
* Crear usuario, hostname y configuración inicial✅
* Primer login al servidor✅

---

### 🔧 Módulo 4 – Configuración básica post-instalación✅

* Actualizar el sistema (`sudo apt update && sudo apt upgrade`)✅
* Instalar herramientas básicas (curl, net-tools, htop, git)✅
* Configurar red (IP estática)✅
Antigua gateway: 192.168.31.2 ip: 192.168.31.129
Nueva: gateway: 192.168.31.2 ip: 192.168.31.100
* Acceso remoto con **SSH**✅
* Comandos básicos de administración (crear usuarios, permisos, etc.)✅

---

### 🌐 Módulo 5 – Servidor Web con Apache o Nginx✅

* ¿Qué es un servidor web?✅
* Instalar y configurar **Apache o Nginx**✅
* Probar con una página HTML básica✅
* Cómo acceder desde otro dispositivo en tu red local✅

---

### ☁️ Módulo 6 – Instalar tu propia nube con Nextcloud✅

* ¿Qué es Nextcloud?✅
* Instalar PHP, MariaDB y Apache✅
---------------------------------------------------
# Instalacion de PHP
sudo apt install php php-gd php-mysql php-curl php-mbstring php-intl php-gmp php-bcmath php-xml php-imagick php-zip php-apcu php-json -y

# Instalacion de MariaDB
sudo apt install mariadb-server -y

# Crear Base de datos en MariaDB

CREATE DATABASE nextcloud;
CREATE USER 'nextclouduser'@'localhost' IDENTIFIED BY '.nysde';
GRANT ALL PRIVILEGES ON nextcloud.* TO 'nextclouduser'@'localhost';
FLUSH PRIVILEGES;
EXIT;

# Releases de nextcloud
https://download.nextcloud.com/server/releases/latest.tar.bz2

# Codigo de configuracion para nextcloud
sudo nano /etc/apache2/sites-available/nextcloud.conf

<VirtualHost *:80>
    ServerAdmin admin@example.com
    DocumentRoot /var/www/nextcloud
    ServerName 192.168.1.100

    <Directory /var/www/nextcloud/>
        Options +FollowSymlinks
        AllowOverride All
        Require all granted
    </Directory>

    ErrorLog ${APACHE_LOG_DIR}/nextcloud_error.log
    CustomLog ${APACHE_LOG_DIR}/nextcloud_access.log combined
</VirtualHost>


-----------------------------------------------------
* Descargar e instalar Nextcloud en el servidor✅
* Acceso desde navegador y configuración inicial✅

---

### 🗄️ Módulo 7 – Compartir archivos con Samba✅

* ¿Qué es Samba?✅
* Crear carpeta compartida para Windows/Linux✅
* Acceso desde otros dispositivos de la red✅

---

### 🎥 Módulo 8 – Servidor de medios (opcional)✅

* Instalar **Plex** o **Jellyfin** en tu servidor
---------------------------------------------
# Crea un directorio para la clave GPG
sudo mkdir -p /etc/apt/keyrings
# Descarga y guarda la clave GPG de Jellyfin
wget -O- https://repo.jellyfin.org/jellyfin_team.gpg.key | gpg --dearmor | sudo tee /etc/apt/keyrings/jellyfin.gpg
# Agrega el repositorio de Jellyfin
export VERSION_OS="$(awk -F'=' '/^ID=/{ print $NF }' /etc/os-release)"
export VERSION_CODENAME="$(awk -F'=' '/^VERSION_CODENAME=/{ print $NF }' /etc/os-release)"
echo "deb [signed-by=/etc/apt/keyrings/jellyfin.gpg] https://repo.jellyfin.org/${VERSION_OS} ${VERSION_CODENAME} main" | sudo tee /etc/apt/sources.list.d/jellyfin.sources

# Solucion al problema si la un error al actualizar sudo apt update
sudo rm /etc/apt/sources.list.d/jellyfin.sources

sudo mkdir -p /etc/apt/keyrings
wget -O- https://repo.jellyfin.org/jellyfin_team.gpg.key | gpg --dearmor | sudo tee /etc/apt/keyrings/jellyfin.gpg > /dev/null

. /etc/os-release

echo "deb [signed-by=/etc/apt/keyrings/jellyfin.gpg] https://repo.jellyfin.org/$ID $VERSION_CODENAME main" | sudo tee /etc/apt/sources.list.d/jellyfin.list

sudo apt update

---------------------------------------------
* Agregar tu biblioteca de videos, música, fotos✅
* Acceder desde TV, tablet o celular✅

---

### 🔐 Módulo 9 – Seguridad básica✅

* Crear nuevo usuario no-root✅
* Cambiar puerto SSH y desactivar login root✅
* Configurar UFW (firewall básico)✅
* Actualizaciones automáticas✅

---

### 🎯 Módulo 10 – Proyectos finales y recomendaciones

* Qué puedes hacer ahora con tu servidor
* Montar tu propio blog con WordPress
* Instalar un servidor de videojuegos (Minecraft, Valheim, etc.)
* Consejos para hacer backups
* Cómo acceder desde fuera de casa (usando DDNS)

---


