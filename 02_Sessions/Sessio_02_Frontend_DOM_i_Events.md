---
tipus: sessio
numero: 2
setmana: 1
dia_setmana: "Dilluns"
sessio_setmana: "2 de 2"
titol: "Presentació del Projecte i Avaluació + Frontend Web: DOM i Esdeveniments"
data: 2026-09-21 # AVUI!
hores: 2
durada_min: 120
bloc: "01_Desenvolupament_Web"
ra:
  - "RA1"
estat: "En curs"
apunts_a_ensenyar_avui:
  - "[[01_Temari/01_Desenvolupament_Web/02_FRONTEND/01_manipulacio_dom|01. Manipulació del DOM]]"
  - "[[01_Temari/01_Desenvolupament_Web/02_FRONTEND/02_esdeveniments|02. Esdeveniments de l'Usuari]]"
  - "[[01_Temari/01_Desenvolupament_Web/02_FRONTEND/04_joc_interactiu|04. Joc Interactiu (Escenari 1)]]"
apunts_per_a_divendres:
  - "[[01_Temari/01_Desenvolupament_Web/02_FRONTEND/03_orientacio_objectes|03. POO amb JavaScript]]"
  - "[[01_Temari/01_Desenvolupament_Web/02_FRONTEND/05_tractament_json|05. Integració de JSON]]"
labs_associats:
  - "[[03_Exercicis_i_Labs/Enunciats/LAB_01_Configuracio_LAMP_i_SSH|LAB_01: Tancament i resolució de dubtes]]"
  - "[[03_Exercicis_i_Labs/Enunciats/LAB_02_Interactivitat_DOM_Joc|LAB_02: Interactivitat del DOM pel Videojoc (Inici)]]"
projecte_associat:
  - "[[04_Projecte_Videojocs/00_Index_Projecte|Projecte Plataforma de Videojocs]]"
  - "[[04_Projecte_Videojocs/Fites_i_Lliuraments|Cronograma i Fites]]"
  - "[[00_Meta/📋 Tauler_Kanban_Entregables|Tauler Kanban d'Entregables]]"
tags:
  - docencia/sessio
  - setmana/01
  - kick-off-projecte
  - ra/ra1
  - stack/js
---

# 🚀 Sessió 02 (AVUI): Sistema d'Avaluació, Presentació del Projecte i Frontend DOM

> [!IMPORTANT]
> **Data**: Dilluns, 21 de setembre de 2026 (Segona classe del curs) | **Durada**: 120 minuts (2 hores)  
> **Doble Objectiu d'Avui**:
> 1. **Part Institucional i d'Avaluació (30 min)**: Aclarir el sistema de qualificació del mòdul, presentar el projecte anual de la plataforma de videojocs, projectar el **Tauler Kanban d'entregables** i organitzar les parelles de treball.
> 2. **Part Tècnica de Desenvolupament (90 min)**: Ensenyar els apunts de JavaScript/DOM del repositori, programar el primer escenari del videojoc i controlar el moviment d'una nau espacial amb tecles.

---

## 📖 1. Apunts Originals del Temari a Projectar i Explicar Avui

A la carpeta del teu Vault `01_Temari/01_Desenvolupament_Web/02_FRONTEND/` hi ha els apunts de referència. **Avui has de projectar i explicar les següents 2 notes (més l'estructura del joc de la nota 04)**:

### 📄 1.1 [[01_Temari/01_Desenvolupament_Web/02_FRONTEND/01_manipulacio_dom|01_manipulacio_dom.md]] (Dedicar 15 min a projectar-lo)
* **Apartats concrets a ensenyar**:
  1. **"Què és el DOM?"**: Mostra la definició de l'arbre d'elements en memòria generat a partir de l'HTML.
  2. **"1. Selecció d'Elements"**: Explica la diferència entre `document.querySelector('#jugador')` (selecciona 1 element) i `document.querySelectorAll('.enemic')` (retorna un array/NodeList).
  3. **"2. Modificació d'Elements > Modificació del Contingut"**: **Molt important per a ciberseguretat**: Explica per què `textContent` és el mètode segur i per què `innerHTML` és vulnerable a injeccions XSS si rep dades de l'usuari (ho aprofitarem al Tema 3 de Hacking Web).
  4. **"Modificació d'Estils"**: Ensenya `jugador.style.setProperty('left', ...)` i `jugador.style.left = ...`.
  5. **"Afegir i Eliminar Elements"**: Ensenya `document.createElement('div')`, `appendChild()` i `remove()`.

### 📄 1.2 [[01_Temari/01_Desenvolupament_Web/02_FRONTEND/02_esdeveniments|02_esdeveniments.md]] (Dedicar 15 min a projectar-lo)
* **Apartats concrets a ensenyar**:
  1. **"Gestió d'esdeveniments"**: Per què fem servir `addEventListener()` i no atributs HTML antics com `onclick=""`.
  2. **"Esdeveniments de teclat"**: Mostra la taula comparativa entre `keydown` (en prémer) i `keyup` (en deixar anar).
  3. **"L'objecte Event"**: Ensenya la captura del paràmetre `(e) => { ... }`:
     - Com llegir la tecla premuda amb `e.key` (`'ArrowUp'`, `'ArrowDown'`).
     - Per què és imprescindible cridar `e.preventDefault()` per evitar que la barra de desplaçament de la finestra es mogui en prémer les fletxes.

### 📄 1.3 [[01_Temari/01_Desenvolupament_Web/02_FRONTEND/04_joc_interactiu|04_joc_interactiu.md]] (Dedicar 10 min a projectar-lo)
* **Apartats concrets a ensenyar**:
  1. **"Estructura del Projecte"**: Ensenya com s'organitza el directori `/joc`:
     - `index.html` (estructura).
     - `index.css` (estil i mides de l'escenari).
     - `app.js` o `main.js` (lògica de moviment).
  2. **"ESCENARI BÀSIC"**: Projecta la imatge d'exemple de l'escenari per inspirar els alumnes abans de començar el laboratori.

> [!TIP]
> **Què farem amb els altres 2 fitxers de JavaScript?**
> * [[01_Temari/01_Desenvolupament_Web/02_FRONTEND/03_orientacio_objectes|03_orientacio_objectes.md]] i [[01_Temari/01_Desenvolupament_Web/02_FRONTEND/05_tractament_json|05_tractament_json.md]] **es projectaran i explicaran aquest DIVENDRES 25/09 (Sessió 03)**, quan convertirem la nau en una classe de POO i carreguem els ovnis amb JSON.

---

## ⏱️ 2. Cronograma Minut a Minut d'Avui (120 minuts)

```
┌─────────────┬─────────────────────────────────────────────────────────────────┐
│ Minuts      │ Activitat a l'Aula (Dilluns 21/09/2026)                         │
├─────────────┼─────────────────────────────────────────────────────────────────┤
│ 00:00-00:15 │ 1. Explicació de l'Avaluació (5 RAs oficials i percentatges)    │
│ 00:15-00:30 │ 2. Presentació del Projecte Indie, Tauler Kanban i Parelles     │
│ 00:30-00:40 │ 3. Tancament del LAB-01 (com i quan s'entrega l'entorn LAMP)    │
│ 00:40-01:10 │ 4. Projecció dels Apunts: 01_manipulacio_dom i 02_esdeveniments │
│ 01:10-01:45 │ 5. Pràctica guiada (LAB-02): Escenari del joc i nau espacial    │
│             │    • Min 80: Checkpoint 1 (CSS Grid/Flexbox i escenari llest)   │
│             │    • Min 95: Checkpoint 2 (Nau generada amb JS al DOM)          │
│             │    • Min 110: Checkpoint 3 (Moviment suau amb fletxes)          │
│ 01:45-01:55 │ 6. F12 DevTools: Depurar el DOM i veure esdeveniments de teclat │
│ 01:55-02:00 │ 7. Tancament i deures per a Divendres 25/09                     │
└─────────────┴─────────────────────────────────────────────────────────────────┘
```

---

## 📢 3. Guió per a la Part Institucional (Minuts 0 a 40)

### Pas 1: El Sistema d'Avaluació del Mòdul 5023 (Min 0-15)
Explica a la pissarra com s'obté la qualificació oficial:
* **Resultats d'Aprenentatge (RAs)**:
  - **RA1 (20%)**: Desenvolupament web i models d'execució (el que estem fent ara).
  - **RA2 i RA3 (40%)**: Hacking web (OWASP Top 10) i mitigació de vulnerabilitats en codi font.
  - **RA4 (20%)**: Auditoria de seguretat en aplicacions mòbils (Android).
  - **RA5 (20%)**: Desplegament segur amb Docker i CI/CD a Proxmox.
* **Fórmula de nota a l'aula**:
  - **40%**: Laboratoris i pràctiques guiades (LAB-01 a LAB-15).
  - **50%**: El **Projecte Transversal de la Plataforma de Videojocs** (dividit en 3 grans Hitos).
  - **10%**: Actitud, seguiment a classe i defensa tècnica.

### Pas 2: La Narrativa del Projecte i el Tauler Kanban (Min 15-30)
* **La història**: *«Som una empresa de videojocs indie. Tenim diversos minijocs en JavaScript dispersos i la direcció ens encarrega crear una plataforma web centralitzada per a jugadors (amb registre, login, rànquings i API de nivells). Durant el curs, primer la construirem (Fase 1), després la hackejarem entre equips rivals i la blindarem (Fase 2), en provarem la seguretat en mòbil (Fase 3) i finalment la desplegarem en contenidors aïllats amb SSL a Proxmox (Fase 4)»*.
* **Obre a la pantalla el Tauler Kanban**:
  📄 [[00_Meta/📋 Tauler_Kanban_Entregables|📋 Tauler Kanban d'Entregables per Fases]]
  - Mostra'ls les 4 columnes de les fases.
  - Explica'ls que cada targeta diu exactament en quines sessions es treballa i la data límit d'entrega.
* **Organització de parelles**: Que s'agrupin en parelles de 2, escullin nom d'equip i pensin quin joc secundari voldran integrar (Snake, Pong, Memory, Flappy Bird, Laberint, etc.).

### Pas 3: Aclariment sobre el LAB-01 fet divendres (Min 30-40)
* El que van instal·lar divendres (Debian, Apache, MariaDB, PHP i SSH) correspon a la pràctica:
  📄 [[03_Exercicis_i_Labs/Enunciats/LAB_01_Configuracio_LAMP_i_SSH|LAB-01: Desplegament de Servidor LAMP i Entorn Remot SSH]].
* **Com i quan s'entrega?**:
  - Pugen al Classroom un breu PDF amb 2 captures (pàgina Apache des del navegador i VS Code connectat per SSH) i la resposta sobre el perill de `info.php`.
  - **Data límit d'entrega**: **Divendres, 25 de setembre de 2026** (inici de la propera classe).

---

## 💻 4. Live Coding i Projecció d'Apunts (Minuts 40 a 70)

Projecta a la pantalla gegant els apunts de referència i després obre el teu VS Code per programar en viu:

### 1. `index.html` (Contenidor de l'escenari)
```html
<!DOCTYPE html>
<html lang="ca">
<head>
    <meta charset="UTF-8">
    <title>Plataforma de Videojocs - Motor JS</title>
    <link rel="stylesheet" href="estils.css">
</head>
<body>
    <h1>Motor del Joc - Fase 1</h1>
    <div id="pantalla-joc"></div>
    <script src="app.js"></script>
</body>
</html>
```

### 2. `estils.css` (El límit del joc)
```css
#pantalla-joc {
    width: 800px;
    height: 500px;
    background-color: #0d1117;
    border: 3px solid #58a6ff;
    position: relative; /* CRÍTIC: referència per als fills absoluts */
    overflow: hidden;
    margin: 20px auto;
}

.nau {
    width: 40px;
    height: 30px;
    background-color: #3fb950;
    position: absolute;
    border-radius: 4px;
}
```

### 3. `app.js` (Creació dinàmica amb el DOM i captura de tecles)
*(Mostra com apliquem els conceptes de `01_manipulacio_dom.md` i `02_esdeveniments.md`)*:
```javascript
const pantalla = document.querySelector('#pantalla-joc');

const nau = {
    x: 50,
    y: 235,
    velocitat: 15,
    element: null,

    crear() {
        // Concepte de 01_manipulacio_dom.md: createElement + appendChild
        this.element = document.createElement('div');
        this.element.classList.add('nau');
        this.actualitzar();
        pantalla.appendChild(this.element);
    },

    actualitzar() {
        // Concepte de 01_manipulacio_dom.md: style.setProperty
        this.element.style.left = `${this.x}px`;
        this.element.style.top = `${this.y}px`;
    },

    moure(direccio) {
        if (direccio === 'amunt' && this.y > 0) {
            this.y -= this.velocitat;
        } else if (direccio === 'avall' && this.y < (500 - 30)) {
            this.y += this.velocitat;
        }
        this.actualitzar();
    }
};

nau.crear();

// Concepte de 02_esdeveniments.md: addEventListener + e.key + preventDefault
window.addEventListener('keydown', (e) => {
    if (e.key === 'ArrowUp') {
        e.preventDefault(); // Bloqueja l'scroll vertical del navegador
        nau.moure('amunt');
    } else if (e.key === 'ArrowDown') {
        e.preventDefault();
        nau.moure('avall');
    }
});
```

---

## 🧪 5. Treball Pràctic dels Alumnes (Minuts 70 a 105)
Els alumnes obren l'enunciat:
📄 [[03_Exercicis_i_Labs/Enunciats/LAB_02_Interactivitat_DOM_Joc|LAB-02: Interactivitat del DOM pel Videojoc en JavaScript]].
* Connectats per SSH a `/var/www/html/joc/`, creen els fitxers i aconsegueixen que la seva nau es mogui dins del rectangle sense sortir dels límits.

---

## ❓ 6. Preguntes de Control Ràpid (Minuts 105 a 115)
1. *Segons els apunts de `01_manipulacio_dom`, per què recomanem `textContent` davant de `innerHTML`?*  
   → Perquè `innerHTML` parseja etiquetes HTML i és la via directa d'atacs XSS, mentre que `textContent` tracta l'entrada com a text pla inofensiu.
2. *Segons `02_esdeveniments`, per què és imprescindible `e.preventDefault()` en aquest joc?*  
   → Per evitar que les tecles de fletxa desplacin la barra de navegació del navegador.

---

## 📝 7. Tancament i Deures per a Divendres (25/09)
* **Lliurament pendent**: Pujar les evidències de **LAB-01 (LAMP)** abans de divendres.
* **Enllaç amb Divendres (Sessió 03)**: Projectarem els apunts [[01_Temari/01_Desenvolupament_Web/02_FRONTEND/03_orientacio_objectes|03_orientacio_objectes.md]] i [[01_Temari/01_Desenvolupament_Web/02_FRONTEND/05_tractament_json|05_tractament_json.md]] per convertir aquest objecte en classes modulars (`Nau`, `Ovni`) i bucle de joc a 60 FPS amb `requestAnimationFrame`!
