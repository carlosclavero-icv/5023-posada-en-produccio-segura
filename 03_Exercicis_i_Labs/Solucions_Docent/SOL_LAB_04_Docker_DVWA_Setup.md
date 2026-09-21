---
tipus: solucio_docent
codi: "SOL-LAB-04"
exercici_associat: "[[03_Exercicis_i_Labs/Enunciats/LAB_04_Docker_DVWA_Setup|LAB-04]]"
bloc: "02_Hacking_Web"
ra:
  - "RA2"
tags:
  - docencia/solucio
  - ra/ra2
  - eina/docker
---

# 🧑‍🏫 Guia de Correcció i Solució: LAB-04 (Desplegament Docker Labs)

## 🎯 Verificació Ràpida des de la Terminal del Docent
Comprova que els 3 contenidors estan corrent i responen:
```bash
docker ps --format "table {{.Names}}	{{.Status}}	{{.Ports}}"
# Hauries de veure:
# lab-dvwa       Up ...   0.0.0.0:8081->80/tcp
# lab-juice-shop Up ...   0.0.0.0:8082->3000/tcp
# lab-bwapp      Up ...   0.0.0.0:8083->80/tcp
```

## ⚠️ Incidència Freqüent a DVWA
Si l'alumne fa login amb `admin` / `password` i la pantalla surt en blanc o dóna error de base de dades, és perquè no ha clicat el botó inferior **Create / Reset Database**. Cal anar directament a `http://localhost:8081/setup.php`.
