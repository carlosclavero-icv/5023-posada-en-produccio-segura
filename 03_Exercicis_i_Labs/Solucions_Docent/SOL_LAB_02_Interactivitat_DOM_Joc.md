---
tipus: solucio_docent
codi: "SOL-LAB-02"
exercici_associat: "[[03_Exercicis_i_Labs/Enunciats/LAB_02_Interactivitat_DOM_Joc|LAB-02]]"
bloc: "01_Desenvolupament_Web"
ra:
  - "RA1"
tags:
  - docencia/solucio
  - ra/ra1
---

# 🧑‍🏫 Guia de Correcció i Solució: LAB-02 (DOM i POO en JavaScript)

## 📁 Fitxers de Solució Completa de Referència

### 1. `classes.js` (Arquitectura POO Neta)
```javascript
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

class Nau extends ElementJoc {
    constructor(x, y, contenidor) {
        super(x, y, 40, 30, 'nau', contenidor);
        this.velocitat = 10;
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

---

## 🎯 Criteris de Qualificació
* **Excel·lent (9-10)**: Moviment fluid, classes ben definides amb `extends`, neteja d'ovnis que surten de la pantalla sense fuites de memòria, configuració per JSON operativa.
* **Notable (7-8)**: Funciona tot però les classes tenen codi duplicat o no s'eliminen els elements del DOM al sortir de la pantalla.
* **Suficient (5-6)**: La nau es mou però no s'ha implementat la classe `Ovni` o la generació automàtica té fallades.
