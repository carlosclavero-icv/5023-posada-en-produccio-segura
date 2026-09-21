---
tipus: exercici
codi: "LAB-04"
titol: "Desplegament d'Entorns Vulnerables amb Docker (DVWA, Juice Shop, bWAPP)"
bloc: "02_Hacking_Web"
ra:
  - "RA2"
dificultat: "Fàcil"
entorn_requerit: "Docker i Docker Compose a Debian/Linux"
avaluable: true
pes_nota: "3%"
temps_estimat_min: 60
tags:
  - docencia/exercici
  - ra/ra2
  - eina/docker
---

# 🧪 LAB-04: Desplegament d'Entorns Vulnerables amb Docker

> **Codi**: `LAB-04` | **Mòdul**: 5023 | **Durada**: 60 minuts | **Qualificació**: Avaluable (3%)

---

## 🎯 Objectius
* Instal·lar i configurar el motor Docker en un entorn Linux.
* Desplegar tres plataformes de pràctiques de seguretat (DVWA, Juice Shop, bWAPP) mitjançant un fitxer `docker-compose.yml`.
* Inicialitzar les bases de dades de cadascuna de les aplicacions.

---

## 📋 Tasques Pas a Pas

### Tasca 1: Preparació del Fitxer Docker Compose
Al teu directori de treball, crea una carpeta `laboratoris-seguretat/` i copia el fitxer de configuració oficial disponible a:
[[05_Laboratoris_Infra/docker-compose-labs/docker-compose.yml|Configuració Docker Compose de Labs]]

### Tasca 2: Execució dels Contenidors
Aixeca els laboratoris en segon pla:
```bash
docker compose up -d
```
Verifica que els 3 contenidors estan en estat *Up*:
```bash
docker compose ps
```

### Tasca 3: Inicialització de DVWA
1. Obre el navegador a `http://localhost:8081`.
2. Inicia sessió amb `admin` / `password`.
3. Navega fins a la secció inferior i fes clic al botó **Create / Reset Database**.
4. Torna a fer login. Accedeix a **DVWA Security** i estableix el nivell de dificultat a **Low**.

---

## 📤 Evidències a Lliurar
* Captura de la comanda `docker compose ps` mostrant els 3 contenidors actius.
* Captura de pantalla de DVWA amb el missatge d'èxit de la base de dades creada i el nivell de seguretat en **Low**.
