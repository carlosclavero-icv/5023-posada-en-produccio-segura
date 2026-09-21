---
tipus: moc
modul: "5023"
assignatura: "Posada en producció segura"
cicle: "Curs d'Especialització en Ciberseguretat en Entorns de les Tecnologies de la Informació"
curs_academic: "2026-2027"
tags:
  - docencia/moc
  - gestio/curs
---

# 🧭 MOC Principal – Mòdul 5023: Posada en Producció Segura

Benvingut/da al **Vault de Gestió i Docència del Mòdul 5023**. Aquest espai centralitza els apunts teòrics, la planificació sessió a sessió, els enunciats de pràctiques per a l'alumnat i el seguiment dels entregables per fases mitjançant el tauler Kanban.

---

## ⚡ Panell de Gestió Ràpida (Sense Plugins)

| Secció | Descripció | Enllaç |
| :--- | :--- | :--- |
| **📋 Tauler Kanban** | **Tots els entregables organitzats per fases (Plugin Kanban)** | [[00_Meta/📋 Tauler_Kanban_Entregables\|Obrir Tauler Kanban]] |
| **🎯 Currículum i RAs** | Resultats d'Aprenentatge oficials, criteris i ponderacions | [[00_Meta/🎯 Mapeig_RAs_i_Criteris\|Veure RAs i Criteris]] |
| **📅 Diari de Classes** | Taula de seguiment sessió a sessió (2 classes/setmana) | [[00_Meta/📅 Calendari_Sessions\|Obrir Diari de Sessions]] |
| **🧪 Catàleg de Labs** | Exercicis, enunciats per a alumnes i criteris de correcció | [[00_Meta/🧪 Index_Exercicis_Labs\|Catàleg de Pràctiques]] |
| **🎮 Projecte Transversal** | Plataforma de Videojocs (Desenvolupament + Auditoria + CI/CD) | [[04_Projecte_Videojocs/00_Index_Projecte\|Guia del Projecte]] |
| **🏷️ Taxonomia** | Guia d'ús d'etiquetes i metadades per a cerques | [[00_Meta/🏷️ Taxonomia_i_Etiquetes\|Guia d'Etiquetes]] |

---

## 📚 Mapa de Continguts Teòrics (01_Temari)

```
┌────────────────────────────────────────────────────────────────────────┐
│               MÒDUL 5023: POSADA EN PRODUCCIÓ SEGURA                   │
└──────────────────────────────────┬─────────────────────────────────────┘
                                   │
      ┌────────────────────────────┼────────────────────────────┐
      ▼                            ▼                            ▼
┌───────────────────┐    ┌───────────────────┐    ┌───────────────────┐
│ BLOC 1: DEV WEB   │    │ BLOC 2: HACKING   │    │ BLOC 4: DEVSECOPS │
│ 20h - RA1         │    │ 36h - RA2, RA3    │    │ 23h - RA5         │
│ HTML/CSS/JS/PHP   │    │ OWASP, Injeccions │    │ Docker, Nginx SSL │
└─────────┬─────────┘    └─────────┬─────────┘    └─────────┬─────────┘
          │                        │                        │
          └────────────────────────┼────────────────────────┘
                                   ▼
              ┌────────────────────────────────────────┐
              │ 🎮 PROJECTE: PLATAFORMA DE VIDEOJOCS   │
              │ (Fita 1: Dev → Fita 2: Sec → Fita 3: CI/CD)
              └────────────────────────────────────────┘
```

### 🔹 [[01_Temari/00_Recursos_i_Eines/README|00. Recursos Generals i Eines]]
* Recull d'eines de virtualització, distribucions Kali/Debian, aplicacions vulnerables (DVWA, bWAPP, Juice Shop, DIVA) i documentació d'estàndards OWASP.

### 🔹 [[01_Temari/01_Desenvolupament_Web/README|01. Desenvolupament d'Aplicacions Web (RA1 - 20h)]]
* [[01_Temari/01_Desenvolupament_Web/01_INTRO_WEB/README|01.1 Intro Web i Entorns]]: VS Code, extensions, Servidor LAMP, connexió remota SSH.
* [[01_Temari/01_Desenvolupament_Web/02_FRONTEND/README|01.2 Frontend]]: DOM, esdeveniments, POO amb JavaScript, JSON i videojoc d'exemple (*Naus vs Ovnis*).
* [[01_Temari/01_Desenvolupament_Web/03_BACKEND/README|01.3 Backend]]: Formularis (GET/POST), Sessions i Cookies, MySQLi/PDO, API REST i arquitectura MVC en PHP.
* [[04_Projecte_Videojocs/00_Index_Projecte|01.4 Projecte Anual]]: Especificacions de la plataforma web de videojocs.

### 🔹 [[01_Temari/02_Hacking_Web/README|02. Detecció i Explotació de Vulnerabilitats Web (RA2, RA3 - 36h)]]
* [[01_Temari/02_Hacking_Web/01_INTRO_OWASP/README|02.1 Introducció OWASP]]: OWASP Top 10, ASVS Level 2, laboratoris DVWA, Juice Shop, bWAPP i Burp Suite.
* [[01_Temari/02_Hacking_Web/02_INJECTION/README|02.2 Injeccions]]: SQL Injection (clàssica, error-based, union, blind, SQLmap) i XSS (reflected, stored, DOM).
* [[01_Temari/02_Hacking_Web/03_BROKEN_AUTH/README|02.3 Autenticació Trencada]]: Atacs de força bruta (Hydra, Burp Intruder), fallades en sessions i cookies.
* [[01_Temari/02_Hacking_Web/04_AUTH_BYPASS/README|02.4 Bypass d'Autorització]]: LFI/RFI amb PHP wrappers i log poisoning, IDOR i pujada de fitxers maliciosos (webshells).

### 🔹 [[01_Temari/03_Hacking_Mobil/README|03. Hacking Mòbil Android (RA4 - 20h)]]
* Arquitectura Android i format APK.
* Anàlisi estàtica: APKTool, JADX, cerca de credencials i secrets.
* Anàlisi dinàmica: Frida, Objection, bypass d'SSL Pinning i detecció de Root.
* Anàlisi automatitzada amb MobSF i aplicacions vulnerables (DIVA).

### 🔹 [[01_Temari/04_Desplegament_Segur/README|04. Desplegament Segur i DevSecOps (RA5 - 23h)]]
* [[01_Temari/04_Desplegament_Segur/01_Intro_Docker|04.1 Introducció a Docker]]: Virtualització vs Contenidors, arquitectura.
* [[01_Temari/04_Desplegament_Segur/02_Install_Docker|04.2 Instal·lació i Comandes]]: Configuració a Debian.
* [[01_Temari/04_Desplegament_Segur/04_Gestio_Imatges|04.3 Dockerfiles]]: Bones pràctiques, creació d'imatges pròpies.
* [[01_Temari/04_Desplegament_Segur/05_Gestio_Xarxes|04.4 Xarxes Docker]]: Aïllament per capes i resolució DNS.
* [[01_Temari/04_Desplegament_Segur/06_Gestio_Volums|04.5 Volums i Persistència]]: Gestió de dades i còpies de seguretat.
* [[01_Temari/04_Desplegament_Segur/07_Docker_Compose|04.6 Docker Compose]]: Orquestració multicontenidor, Nginx Reverse Proxy amb SSL i pipelines CI/CD amb GitHub Actions.

---

## 📌 Resum d'Entregables del Curs (Taula Pura)

| Fase | Bloc | Entregables Principals | Pes Nota | Estat |
| :---: | :--- | :--- | :---: | :---: |
| **Fase 1** | `01_Desenvolupament_Web` | [[03_Exercicis_i_Labs/Enunciats/LAB_01_Configuracio_LAMP_i_SSH\|LAB-01]], [[03_Exercicis_i_Labs/Enunciats/LAB_02_Interactivitat_DOM_Joc\|LAB-02]], [[03_Exercicis_i_Labs/Enunciats/LAB_03_CRUD_PHP_MySQL\|LAB-03]] i [[04_Projecte_Videojocs/Fites_i_Lliuraments#Fita 1\|Fita 1 Projecte]] | 30% | En curs |
| **Fase 2** | `02_Hacking_Web` | [[03_Exercicis_i_Labs/Enunciats/LAB_04_Docker_DVWA_Setup\|LAB-04]], [[03_Exercicis_i_Labs/Enunciats/LAB_05_SQLi_DVWA\|LAB-05]], LABs XSS/Auth i [[04_Projecte_Videojocs/Fites_i_Lliuraments#Fita 2\|Fita 2 Projecte (Auditoria)]] | 35% | Pendent |
| **Fase 3** | `03_Hacking_Mobil` | Pràctiques APKTool, JADX, MobSF, Frida i informe d'auditoria mòbil | 20% | Pendent |
| **Fase 4** | `04_Desplegament_Segur` | Pràctiques Dockerfile, Compose, Nginx SSL i [[04_Projecte_Videojocs/Fites_i_Lliuraments#Fita 3\|Fita 3 Final (CI/CD)]] | 35% | Pendent |

> Per gestionar i moure els lliuraments visualment en columnes, utilitza el fitxer dedicat: [[00_Meta/📋 Tauler_Kanban_Entregables|📋 Tauler Kanban d'Entregables]].
