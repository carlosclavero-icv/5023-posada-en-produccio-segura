---
tipus: projecte
titol: "Rúbrica d'Avaluació del Projecte"
modul: "5023"
tags:
  - docencia/projecte
  - avaluacio/rubrica
---

# 📊 Rúbrica d'Avaluació del Projecte de Videojocs

Aquesta rúbrica s'utilitzarà per avaluar les 3 fites del projecte transversal del mòdul 5023.

---

## ⚖️ Ponderació Global

* **Funcionalitat i Compliment de Requisits**: **40%**
* **Arquitectura, Qualitat del Codi i Seguretat**: **30%**
* **Interfície d'Usuari i Experiència (UI/UX)**: **20%**
* **Documentació Tècnica i Defensa Oral**: **10%**

---

## 📋 Taula Detallada de Criteris

| Dimensió | Excel·lent (9-10) | Notable (7-8) | Aprovat (5-6) | Insuficient (0-4) |
| :--- | :--- | :--- | :--- | :--- |
| **Funcionalitat (40%)** | Tots els requisits funcionals (registre, login, videojoc multinivell, API REST, rànquings) funcionen de forma impecable i sense errors d'execució. | Funciona el joc i l'autenticació, però hi ha algun detall menor que falla a l'API o a les puntuacions. | L'aplicació és bàsica, el joc funciona però té mecàniques incompletes o fallades de persistència. | L'aplicació no funciona, fallades greus al login o no connecta amb la base de dades. |
| **Codi i Seguretat (30%)** | Codi net, modular (MVC), comentat i seguint bones pràctiques. Totes les consultes usen sentències preparades. Resistent a atacs SQLi, XSS, CSRF i IDOR. Desplegament Docker impecable amb xarxes aïllades. | Codi ben estructurat. Seguretat aplicada correctament en els punts crítics (SQLi resolt). Contenidors funcionals amb alguna millora possible en xarxes o gestió de secrets. | Codi desordenat o poc comentat. Seguretat bàsica aplicada amb deficiències (algun vector SQLi o XSS encara vulnerable). Docker funciona però amb configuració mínima. | Codi espaghetti sense estructura. Vulnerable a injeccions evidents. Els contenidors no aixequen o no hi ha aïllament. |
| **Interfície i UX (20%)** | Disseny modern, professional, adaptat a dispositius mòbils, joc fluid, controls intuïtius i bona retroacció a l'usuari. | Interfície neta i agradable. El joc és fàcilment jugable sense manuals complexos. | Disseny bàsic sense estil cuidat, responsive limitat, mecàniques de joc tosces. | Interfície trencada, textos desbordats o controls inoperatius. |
| **Documentació i Defensa (10%)** | Documentació completa (diagrama ER, endpoints de l'API, arquitectura Docker, informe d'auditoria). Defensa oral clara, tècnica i segura. | Documentació correcta amb petits buits. Bona defensa del projecte. | Documentació incompleta (manca algun diagrama o endpoint). Defensa superficial. | Documentació inexistent o copiada. Incapaç de respondre preguntes tècniques del seu propi codi. |
