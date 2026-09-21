---
tipus: curriculum
modul: "5023"
nom: "Posada en producció segura"
hores_totals: 99
tags:
  - docencia/curriculum
  - fp/avaluacio
---

# 🎯 Mapeig de Resultats d'Aprenentatge (RA) i Criteris d'Avaluació

En aquesta guia es detallen els 5 Resultats d'Aprenentatge oficials del mòdul **5023: Posada en producció segura** i com es vinculen amb les unitats temàtiques, sessions i pràctiques d'aquest Vault.

---

## 📋 Taula Resum de RAs

| RA | Enunciat Oficial | Hores | Bloc Associat | Pes % Aprox. |
| :---: | :--- | :---: | :--- | :---: |
| **RA1** | Prova aplicacions web i aplicacions per a dispositius mòbils analitzant l'estructura del codi i el seu model d'execució. | 20h | `01_Desenvolupament_Web` | 20% |
| **RA2** | Determina el nivell de seguretat requerit per aplicacions identificant els vectors d'atac habituals i els seus riscos associats. | 18h | `02_Hacking_Web` (Intro i OWASP) | 20% |
| **RA3** | Detecta i corregeix vulnerabilitats d'aplicacions web analitzant el seu codi font i configurant servidors web. | 18h | `02_Hacking_Web` (Injeccions i Correccions) | 20% |
| **RA4** | Detecta problemes de seguretat en les aplicacions per a dispositius mòbils, monitoritzant la seva execució i analitzant fitxers i dades. | 20h | `03_Hacking_Mobil` | 20% |
| **RA5** | Implanta sistemes segurs de desplegat de programari, utilitzant eines per a l’automatització de la construcció dels seus elements. | 23h | `04_Desplegament_Segur` | 20% |

---

## 🔍 Detall Curricular per RA

### RA1 – Proves d'aplicacions web i mòbils (20 hores)
* **Objectiu**: Comprendre l'arquitectura client-servidor, desenvolupar aplicacions web bàsiques (frontend i backend) i analitzar l'execució del codi font.
* **Continguts clau**:
  - Servidor LAMP (Linux, Apache, MySQL, PHP) i entorn VS Code remot.
  - HTML5 semàntic, CSS3 modern i JavaScript avançat (DOM, Events, POO, JSON).
  - Backend PHP amb gestió de formularis, cookies i sessions.
  - Connexió PDO/MySQLi i creació d'una API REST.
  - Arquitectura Model-Vista-Controlador (MVC).
* **Evidència principal**: Desenvolupament de la base de la plataforma de videojocs ([[04_Projecte_Videojocs/00_Index_Projecte|Fase 1 del Projecte]]).

### RA2 – Determinació del nivell de seguretat i riscos (18 hores)
* **Objectiu**: Identificar els vectors d'atac més habituals, avaluar el risc de vulnerabilitats i aplicar estàndards com OWASP Top 10 i ASVS.
* **Continguts clau**:
  - OWASP Top 10 Web i ASVS (Application Security Verification Standard) Nivell 2.
  - Eines d'intercepció i exploració de vectors (Burp Suite, proxies HTTP).
  - Configuració de laboratoris d'auditoria (DVWA, Juice Shop, bWAPP).
  - Classificació de riscos (CVSS, severitat, impacte).

### RA3 – Detecció i correcció de vulnerabilitats web (18 hores)
* **Objectiu**: Detectar punts febles en el codi font i configuració del servidor web, explotar-los en entorns controlats i aplicar pedaços de seguretat.
* **Continguts clau**:
  - Injeccions SQL (SQLi) manuals i automatitzades (SQLmap) → Correcció amb *Prepared Statements*.
  - Cross-Site Scripting (XSS) reflected, stored i DOM → Correcció amb sanitització i CSP.
  - Atacs d'autenticació i sessions (força bruta, fixació, segrest) → Correcció amb polítiques de cookies i contrasenyes.
  - Bypass d'autorització, LFI/RFI i pujada de fitxers maliciosos → Correcció de fluxos i whitelists.
* **Evidència principal**: Informe d'auditoria i correcció del projecte propi ([[04_Projecte_Videojocs/00_Index_Projecte|Fase 2 del Projecte]]).

### RA4 – Seguretat en aplicacions mòbils (20 hores)
* **Objectiu**: Analitzar la seguretat d'aplicacions mòbils (Android), auditant el paquet APK, la memòria i les comunicacions.
* **Continguts clau**:
  - Anàlisi estàtica de codi font amb APKTool i JADX.
  - Detecció de credencials exposades, permisos excessius i components exportats.
  - Anàlisi dinàmica amb emuladors, Frida i Objection (bypasses de seguretat).
  - Anàlisi automàtica amb MobSF i estàndard OWASP MASVS / MSTG.

### RA5 – Desplegament segur i DevSecOps (23 hores)
* **Objectiu**: Automatitzar la construcció i desplegament d'aplicacions utilitzant contenidors i pipelines CI/CD amb bones pràctiques de seguretat.
* **Continguts clau**:
  - Contenidors Docker: imatges oficials, Dockerfiles no-root i optimització de capes.
  - Segmentació de xarxes Docker (frontend pública, backend aïllada).
  - Persistència segura amb volums Docker i estratègies de còpies de seguretat.
  - Orquestració amb Docker Compose i Nginx com a Reverse Proxy amb xifratge SSL.
  - Automatització del desplegament amb GitHub Actions i runners a Proxmox VE.
* **Evidència principal**: Posada en producció automatitzada de la plataforma de videojocs ([[04_Projecte_Videojocs/00_Index_Projecte|Fase 3 del Projecte]]).
