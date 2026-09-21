---
tipus: sessio
numero: 3
setmana: 2
dia_setmana: "Divendres"
sessio_setmana: "1 de 2"
titol: "POO en JavaScript, Jerarquia de Classes, Game Loop i Nivells en JSON"
data: 2026-09-25
hores: 2
durada_min: 120
bloc: "01_Desenvolupament_Web"
ra:
  - "RA1"
estat: "Pendent"
apunts_a_ensenyar_avui:
  - "[[01_Temari/01_Desenvolupament_Web/02_FRONTEND/03_orientacio_objectes|03. Programació Orientada a Objectes amb JavaScript]]"
  - "[[01_Temari/01_Desenvolupament_Web/02_FRONTEND/04_joc_interactiu|04. Joc Interactiu (Game Loop i Col·lisions)]]"
  - "[[01_Temari/01_Desenvolupament_Web/02_FRONTEND/05_tractament_json|05. Integració de JSON amb JavaScript]]"
codi_exemple_a_ensenyar:
  - "[[01_Temari/01_Desenvolupament_Web/02_FRONTEND/03_joc_complet|Carpeta d'Exemple: 03_joc_complet]]"
labs_associats:
  - "[[03_Exercicis_i_Labs/Enunciats/LAB_01_Configuracio_LAMP_i_SSH|LAB-01: Lliurament Avui (Data Límit)]]"
  - "[[03_Exercicis_i_Labs/Enunciats/LAB_02_Interactivitat_DOM_Joc|LAB-02: Interactivitat del DOM pel Videojoc (Part 2 - Classes i Bucle)]]"
projecte_associat:
  - "[[04_Projecte_Videojocs/00_Index_Projecte|Projecte Plataforma de Videojocs]]"
  - "[[00_Meta/📋 Tauler_Kanban_Entregables|Tauler Kanban]]"
tags:
  - docencia/sessio
  - setmana/02
  - ra/ra1
  - stack/js
---

# 🚀 Sessió 03: POO en JavaScript, Game Loop a 60 FPS i Nivells en JSON

> [!NOTE]
> **Data**: Divendres, 25 de setembre de 2026 (Classe 1 de 2 de la Setmana 2) | **Durada**: 120 minuts (2 hores)  
> **Resultat d'Aprenentatge**: [[00_Meta/🎯 Mapeig_RAs_i_Criteris#RA1|RA1 - Estructuració modular de codi, model d'execució i POO]]  
> 📥 **Recollida d'evidències**: Avui finalitza el termini per lliurar el [[03_Exercicis_i_Labs/Enunciats/LAB_01_Configuracio_LAMP_i_SSH|LAB-01 (LAMP i SSH)]].

---

## 📖 1. Apunts Originals del Temari a Projectar i Explicar Avui

En aquesta sessió cobrim els 3 fitxers d'apunts de la carpeta `01_Temari/01_Desenvolupament_Web/02_FRONTEND/` que transformen la nau simple del dilluns en un motor de videojoc professional:

### 📄 1.1 [[01_Temari/01_Desenvolupament_Web/02_FRONTEND/03_orientacio_objectes|03_orientacio_objectes.md]] (Projectar min 15 a 35)
* **Apartats concrets a ensenyar al proyector**:
  1. **"Fonaments de la POO"**:
     - *Abstracció*: Com modelar elements d'un joc identificant atributs (posició `x`, `y`, velocitat) i mètodes (`dibuixar()`, `moure()`).
     - *Classe vs Objecte*: La classe com a plantilla i els objectes com a instàncies vives a la memòria RAM del navegador.
  2. **"Sintaxi moderna de classes en ES6"**:
     - Estructura `class ElementJoc { constructor(x, y, w, h, ...) { ... } }`.
     - Ús de `this` per referenciar la instància actual.
  3. **"Herència (`extends` i `super`)"**:
     - Mostrar com `class Nau extends ElementJoc` i `class Ovni extends ElementJoc` reutilitzen el constructor i mètodes de la classe mare cridant `super(...)`.

### 📄 1.2 [[01_Temari/01_Desenvolupament_Web/02_FRONTEND/04_joc_interactiu|04_joc_interactiu.md]] (Projectar min 35 a 55)
* **Apartats concrets a ensenyar al proyector**:
  1. **"El Bucle de Joc (Game Loop)"**:
     - Explicar per què **mai s'ha d'usar `setInterval`** per moure personatges (no se sincronitza amb la pantalla i causa parpellejos).
     - Mostrar l'ús de `requestAnimationFrame(bucleJoc)`: el navegador l'executa a la taxa nativa de refresc (60 FPS) i s'atura sol si l'usuari canvia de pestanya (estalvi de CPU).
  2. **"Generació d'enemics en un vector"**:
     - Com instanciar ovnis cada cert temps i desar-los a `const enemics = []`.
     - Neteja de memòria: per què és vital fer `element.remove()` i `enemics.splice(i, 1)` quan surten de la pantalla per evitar fuites de memòria (*Memory Leaks*).
  3. **"Detecció de Col·lisions"**:
     - Projectar l'algorisme de Bounding Box (superposició de caixes AABB - Axis-Aligned Bounding Box).

### 📄 1.3 [[01_Temari/01_Desenvolupament_Web/02_FRONTEND/05_tractament_json|05_tractament_json.md]] (Projectar min 55 a 65)
* **Apartats concrets a ensenyar al proyector**:
  1. **"Casos d'ús amb JSON en videojocs"**: Configuració de nivells (vides, velocitat de desplaçament, nombre d'ovnis per onada).
  2. **"JSON.parse() i JSON.stringify()"**: Com convertir una cadena de text en un objecte JavaScript operable.
  3. Mostrar l'estructura del fitxer `nivell.json` que carregarem al joc.

---

## ⏱️ 2. Cronograma Minut a Minut (120 minuts)

```
┌─────────────┬─────────────────────────────────────────────────────────────────┐
│ Minuts      │ Activitat a l'Aula (Divendres 25/09/2026)                       │
├─────────────┼─────────────────────────────────────────────────────────────────┤
│ 00:00-00:15 │ 1. Repàs i recollida de LAB-01 (comprovació d'entregues)        │
│ 00:15-00:35 │ 2. Projecció apunts 03_orientacio_objectes: Classes i herència  │
│ 00:35-00:55 │ 3. Projecció apunts 04_joc_interactiu: Game Loop i col·lisions   │
│ 00:55-01:05 │ 4. Projecció apunts 05_tractament_json: Càrrega de nivells       │
│ 01:05-01:45 │ 5. Pràctica guiada (LAB-02 Part 2): classes.js i bucle de joc    │
│             │    • Min 80: Checkpoint 1 (Refactor de Nau amb classe ES6)      │
│             │    • Min 95: Checkpoint 2 (Generació d'ovnis en bucle 60 FPS)   │
│             │    • Min 115: Checkpoint 3 (Col·lisió nau-ovni i marcatge)     │
│ 01:45-01:55 │ 6. DevTools Performance: Comprovar que no hi ha caigudes de FPS│
│ 01:55-02:00 │ 7. Tancament i connexió amb el Backend PHP del dilluns          │
└─────────────┴─────────────────────────────────────────────────────────────────┘
```

---

## 🖼️ 3. Esquemes per a la Pissarra (Whiteboard)

Dibuixa aquest diagrama a la pissarra durant els minuts 15 a 30:

```
                  ┌──────────────────────────────────────────────┐
                  │                 ElementJoc                   │
                  │ ──────────────────────────────────────────── │
                  │ - x, y, w, h                                 │
                  │ - contenidor, elementDOM                     │
                  │ ──────────────────────────────────────────── │
                  │ + dibuixar()                                 │
                  │ + eliminar()                                 │
                  └──────────────────────┬───────────────────────┘
                                         │
                        ┌────────────────┴────────────────┐
                        │ (extends + super())             │ (extends + super())
                        ▼                                 ▼
         ┌─────────────────────────────┐   ┌─────────────────────────────┐
         │             Nau             │   │            Ovni             │
         │ ─────────────────────────── │   │ ─────────────────────────── │
         │ - vides: 3                  │   │ - velocitat: number         │
         │ ─────────────────────────── │   │ ─────────────────────────── │
         │ + moureAmunt()              │   │ + moure()                   │
         │ + moureAvall()              │   │ + esFora(): boolean         │
         └─────────────────────────────┘   └─────────────────────────────┘
```

---

## 💻 4. Guió de Live Coding del Docent (Codi pas a pas)

Mostra als alumnes la separació de fitxers a `/var/www/html/joc/`:

### 1. `classes.js` (Jerarquia modular neta)
```javascript
// Classe Mare: Tots els elements visuals de la pantalla
class ElementJoc {
    constructor(x, y, w, h, cssClass, contenidor) {
        this.x = x;
        this.y = y;
        this.w = w;
        this.h = h;
        this.contenidor = contenidor;
        
        this.element = document.createElement('div');
        this.element.classList.add(cssClass);
        this.element.style.width = `${w}px`;
        this.element.style.height = `${h}px`;
        this.dibuixar();
        this.contenidor.appendChild(this.element);
    }
    
    dibuixar() {
        this.element.style.left = `${this.x}px`;
        this.element.style.top = `${this.y}px`;
    }
    
    eliminar() {
        this.element.remove();
    }
}

// Classe Filla: Nau del jugador
class Nau extends ElementJoc {
    constructor(x, y, contenidor) {
        super(x, y, 40, 30, 'nau', contenidor);
        this.velocitat = 12;
        this.vides = 3;
    }
    
    moureAmunt() {
        if (this.y > 0) {
            this.y -= this.velocitat;
            this.dibuixar();
        }
    }
    
    moureAvall(alcadaMax) {
        if (this.y < alcadaMax - this.h) {
            this.y += this.velocitat;
            this.dibuixar();
        }
    }
}

// Classe Filla: Enemics que apareixen per la dreta
class Ovni extends ElementJoc {
    constructor(x, y, velocitat, contenidor) {
        super(x, y, 35, 35, 'ovni', contenidor);
        this.velocitat = velocitat;
    }
    
    moure() {
        this.x -= this.velocitat;
        this.dibuixar();
    }
    
    esFora() {
        return this.x < -this.w;
    }
}
```

### 2. Algorisme de Detecció de Col·lisió (Bounding Box)
```javascript
function hiHaColisio(a, b) {
    return !(
        a.y + a.h < b.y ||
        a.y > b.y + b.h ||
        a.x + a.w < b.x ||
        a.x > b.x + b.w
    );
}
```

---

## 🧪 5. Treball Pràctic dels Alumnes (Minuts 65 a 105)

Els alumnes continuen amb l'enunciat:
📄 [[03_Exercicis_i_Labs/Enunciats/LAB_02_Interactivitat_DOM_Joc|LAB-02: Interactivitat del DOM pel Videojoc (Part 2)]].

### Fites d'avui a les taules:
1. **Checkpoint 1 (min 80)**: Tenir separat el codi a `classes.js` i instanciar la `Nau` des de `app.js`.
2. **Checkpoint 2 (min 95)**: Implementar la funció `spawnOvni()` amb `setInterval` cada 1.5s i el bucle `requestAnimationFrame(gameLoop)` que mou tots els ovnis cap a l'esquerra.
3. **Checkpoint 3 (min 115)**: Comprovar la col·lisió: quan un ovni toca la nau, l'ovni s'elimina i es resta 1 vida al marcador.

---

## ❓ 6. Preguntes de Control Conceptual

1. **Pregunta**: *Per què és obligatori cridar `super()` a la primera línia del constructor de la classe `Nau`?*  
   → Perquè crida el constructor de la classe mare (`ElementJoc`). Sense `super()`, JavaScript no inicialitza l'objecte `this` i llança un error fatal de tipus `ReferenceError`.
2. **Pregunta**: *Què passa si fem `ovni.element.remove()` però no l'eliminem de l'array `enemics.splice(i, 1)`?*  
   → L'element visual desapareix de la pantalla, però l'objecte JS continua viu a la memòria RAM de l'array i el bucle continuarà intentant moure'l en cada fotograma, consumint CPU inútilment.
3. **Pregunta**: *Per què el format JSON no admet funcions ni comentaris?*  
   → Perquè JSON està dissenyat estrictament com un estàndard universal de dades (intercanvi entre diferents llenguatges), no com un llenguatge executable.

---

## ⚠️ 7. Troubleshooting a l'Aula (Solucions en 30 segons)

| Símptoma | Causa real | Solució en 30 segons |
| :--- | :--- | :--- |
| `Uncaught ReferenceError: ElementJoc is not defined` | A `index.html`, l'script `app.js` està escrit abans que `classes.js`. | Invertir l'ordre a `index.html`: primer `<script src="classes.js"></script>` i després `app.js`. |
| El joc va excessivament lent al cap de 2 minuts de partida. | No s'estan eliminant els ovnis que surten de la pantalla. L'array `enemics` té milers d'elements. | Dins del bucle: si `ovni.esFora()`, fer `ovni.eliminar()` i `enemics.splice(i, 1)`. |
| La nau o els ovnis es mouen a salts molt bruscos. | S'ha combinat una transició CSS (`transition: all`) amb el moviment continu per JavaScript. | Eliminar qualsevol propietat `transition` del fitxer `estils.css` per a les classes `.nau` i `.ovni`. El moviment continu el gestiona JS frame a frame. |

---

## 📝 8. Tancament, Entregables i Connexió

* **Estat d'entregues**: Avui recollim el **LAB-01 (LAMP)**.
* **Propera entrega**: El **LAB-02 (Joc en JS)** es lliurarà el proper **Divendres 02/10/2026** (inici de la Sessió 05).
* **Enllaç amb Dilluns 28/09 (Sessió 04)**: El nostre joc és jugable al navegador, però si tanquem la finestra les puntuacions desapareixen. Dilluns farem el salt al **Backend amb PHP**, crearem el sistema de login i aprendrem la gestió de sessions i cookies!

---

## 🧑‍🏫 9. Codi Màster de Referència per al Docent

Si un alumne té un error greu de bucle, projecta o revisa el bucle estàndard:
```javascript
// Bucle principal del joc a 60 FPS
function gameLoop() {
    for (let i = enemics.length - 1; i >= 0; i--) {
        const ovni = enemics[i];
        ovni.moure();
        
        // Comprovar col·lisió
        if (hiHaColisio(nau, ovni)) {
            ovni.eliminar();
            enemics.splice(i, 1);
            nau.vides--;
            document.querySelector('#vides').textContent = nau.vides;
            if (nau.vides <= 0) {
                alert("Game Over!");
                return;
            }
        } else if (ovni.esFora()) {
            ovni.eliminar();
            enemics.splice(i, 1);
        }
    }
    requestAnimationFrame(gameLoop);
}
requestAnimationFrame(gameLoop);
```
