---
tipus: exercici
codi: "LAB-01"
titol: "Desplegament de Servidor LAMP i Entorn Remot SSH"
bloc: "01_Desenvolupament_Web"
ra:
  - "RA1"
dificultat: "Fàcil"
entorn_requerit: "Màquina Virtual Debian 12 a VirtualBox"
avaluable: true
pes_nota: "3%"
temps_estimat_min: 90
tags:
  - docencia/exercici
  - ra/ra1
  - stack/lamp
---

# 🧪 LAB-01: Desplegament de Servidor LAMP i Entorn Remot SSH

> **Codi**: `LAB-01` | **Mòdul**: 5023 | **Durada**: 90 minuts | **Qualificació**: Avaluable (3%)

---

## 🎯 Objectius Pedagògics
* Desplegar la pila de software LAMP (Linux, Apache, MariaDB, PHP) en una màquina virtual Debian.
* Securitzar l'accés remot mitjançant parelles de claus SSH.
* Configurar l'extensió **Remote - SSH** de Visual Studio Code per editar fitxers directament al servidor.

---

## 🛠️ Prerequisits
* Màquina Virtual amb Debian 12 en funcionament amb xarxa en mode **Adaptador Pont (Bridge)** o **Xarxa Nat / Host-Only** amb accés des de l'equip amfitrió.

---

## 📋 Tasques Pas a Pas

### Tasca 1: Instal·lació de la Pila LAMP
Accedeix a la terminal del teu servidor Debian i executa:
```bash
sudo apt update && sudo apt upgrade -y
sudo apt install apache2 mariadb-server php libapache2-mod-php php-mysql openssh-server -y
```

Verifica que el servidor web Apache està en marxa:
```bash
sudo systemctl status apache2
```

Obre el navegador de la teva màquina física i accedeix a `http://<IP_DEBIAN>/`. Hauries de visualitzar la pàgina per defecte d'Apache.

### Tasca 2: Comprovació del Mòdul PHP
Crea un fitxer de diagnòstic a l'arrel web:
```bash
echo "<?php phpinfo(); ?>" | sudo tee /var/www/html/info.php
```
Accedeix a `http://<IP_DEBIAN>/info.php` i comprova la versió de PHP instal·lada.
*Un cop comprovat, elimina el fitxer per motius de seguretat:*
```bash
sudo rm /var/www/html/info.php
```

### Tasca 3: Configuració de Permisos Web
Assigna els permisos del directori `/var/www/html` al teu usuari habitual per poder editar codi sense usar `sudo`:
```bash
sudo chown -R $USER:www-data /var/www/html
sudo chmod -R 775 /var/www/html
```

### Tasca 4: Configuració de VS Code Remote SSH
1. Genera una clau SSH des del teu equip amfitrió si no en tens: `ssh-keygen -t ed25519`.
2. Copia la clau pública a la màquina Debian: `ssh-copy-id usuari@<IP_DEBIAN>`.
3. A VS Code, instal·la l'extensió **Remote - SSH**.
4. Connecta't a la màquina Debian i obre la carpeta `/var/www/html`.

---

## 📤 Evidències a Lliurar
Crea un document PDF o Markdown al Classroom amb:
1. Captura de la pàgina per defecte d'Apache accessible des del navegador físic.
2. Captura de pantalla de Visual Studio Code connectat per SSH editant un fitxer `test.html` a `/var/www/html`.
3. Resposta raonada: *Per què deixar actiu el fitxer `info.php` en un entorn de producció suposa un risc greu de seguretat? (Cita quina informació revela a un potencial atacant).*
