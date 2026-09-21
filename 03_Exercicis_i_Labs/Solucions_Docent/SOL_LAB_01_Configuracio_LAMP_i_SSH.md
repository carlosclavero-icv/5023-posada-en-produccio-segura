---
tipus: solucio_docent
codi: "SOL-LAB-01"
exercici_associat: "[[03_Exercicis_i_Labs/Enunciats/LAB_01_Configuracio_LAMP_i_SSH|LAB-01]]"
bloc: "01_Desenvolupament_Web"
ra:
  - "RA1"
tags:
  - docencia/solucio
  - ra/ra1
---

# 🧑‍🏫 Guia de Correcció i Solució: LAB-01 (LAMP i SSH)

## 🎯 Criteris Ràpids de Verificació Visual a l'Aula
1. **Comprovació d'Apache**: Obrir des de l'equip del docent `http://<IP_ALUMNE>/` → Pàgina per defecte d'Apache.
2. **Comprovació de Permisos**: Mirar que `/var/www/html/` pertanyi a l'usuari no-root de l'alumne (`ls -ld /var/www/html`).
3. **Comprovació de Seguretat**: Verificar que `info.php` hagi estat eliminat (`curl -I http://<IP_ALUMNE>/info.php` ha de retornar 404 Not Found).

---

## 💻 Script de Resolució d'un Sol Cop (Per si una VM falla)
Si una màquina d'un alumne es desconfigura completament, pots fer-li executar aquest bloc per recuperar l'estat en 1 minut:
```bash
sudo apt update && sudo apt install -y apache2 mariadb-server php libapache2-mod-php php-mysql openssh-server
sudo chown -R $USER:www-data /var/www/html
sudo chmod -R 775 /var/www/html
sudo systemctl restart apache2 mariadb ssh
```

---

## 📝 Resposta Model a la Pregunta d'Evidència
* **Pregunta**: *Per què deixar actiu `info.php` en un entorn de producció suposa un risc greu de seguretat?*
* **Resposta 10/10**: Perquè proporciona informació exhaustiva de la fase de reconeixement (*Reconnaissance*) a un atacant:
  1. La versió exacta del kernel Linux i de PHP (permet buscar vulnerabilitats conegudes o CVEs específics).
  2. Rutes internes del servidor (`SCRIPT_FILENAME`, directori arrel), facilitant atacs de *Path Traversal* o *LFI*.
  3. Directives de seguretat de `php.ini` com `allow_url_fopen`, `allow_url_include` o `disable_functions`.
  4. Variables d'entorn del sistema (`$_SERVER` i `$_ENV`), que en molts servidors contenen claus d'API, credencials de base de dades o secrets del sistema.
