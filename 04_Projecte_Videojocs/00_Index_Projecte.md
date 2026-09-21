---
tipus: projecte
titol: "Projecte Transversal: Plataforma Web de Videojocs"
modul: "5023"
durada_aula: "30 hores"
organitzacio: "Treball per parelles"
tags:
  - docencia/projecte
  - projecte/videojocs
  - ra/ra1
  - ra/ra3
  - ra/ra5
---

# 🎮 Projecte Anual: Plataforma de Videojocs Web

El projecte del Mòdul 5023 té com a objectiu dissenyar, desenvolupar, auditar i desplegar de forma segura una **plataforma web completa de videojocs**.

Aquest projecte articula transversalment tot el curs en 3 grans fites coincidents amb els blocs de contingut:
1. **Bloc 1 (10h a l'aula)**: Desenvolupament de l'aplicació (Frontend en JS, Backend PHP, BBDD MySQL i API REST). → **RA1**
2. **Bloc 2 (8h a l'aula)**: Auditoria creuada de seguretat web, detecció de vulnerabilitats OWASP i correcció de codi. → **RA2, RA3**
3. **Bloc 4 (12h a l'aula)**: Containerització completa amb Docker, xarxes aïllades, reverse proxy Nginx amb SSL i CI/CD a Proxmox amb GitHub Actions. → **RA5**

---

## 📑 Documents de Gestió del Projecte

* 📄 [[04_Projecte_Videojocs/projecte_plataforma_videojocs|Enunciat Tècnic Complet i Especificacions]]: Document original complet amb detalls d'arquitectura, endpoints de l'API i regles dels jocs.
* 🚩 [[04_Projecte_Videojocs/Fites_i_Lliuraments|Calendari de Fites i Lliuraments]]: Dates clau i entregables per a cada fase.
* 📊 [[04_Projecte_Videojocs/Rubrica_Avaluacio|Rúbrica d'Avaluació]]: Criteris detallats de qualificació (40% funcionalitat, 30% arquitectura/codi, 20% UI/UX, 10% documentació).
* 🛡️ [[01_Temari/01_Desenvolupament_Web/04_PROJECTE/projecte_plataforma_videojocs#checklist-de-seguretat|Checklist de Seguretat]]: Guia de verificació de controls defensius abans del pas a producció.

---

## 🏗️ Arquitectura Objectiu (Desplegament Final)

```
┌────────────────────────────────────────────────────────┐
│              NGINX (Reverse Proxy + SSL)               │
│                     Port 80 / 443                      │
└───────────────┬────────────────────────┬───────────────┘
                │                        │
       (frontend-network)       (frontend-network)
                │                        │
                ▼                        ▼
     ┌─────────────────────┐  ┌─────────────────────┐
     │   FRONTEND WEB      │  │   BACKEND API       │
     │   (HTML/CSS/JS)     │  │   (PHP 8.x + Apache)│
     │   Nginx Alpine      │  │   php:8.2-apache    │
     └─────────────────────┘  └──────────┬──────────┘
                                         │
                                  (backend-network)
                                         │
                                         ▼
                              ┌─────────────────────┐
                              │    BASE DE DADES    │
                              │    MySQL / MariaDB  │
                              │ (Sense exposar port)│
                              └─────────────────────┘
```
