---
tipus: guia_docent
titol: "Estàndard i Prompt de Disseny de Sessions de Classe (Mòdul 5023)"
modul: "5023"
durada_classe: "2 hores (120 minuts)"
dies_classe: "Dilluns i Divendres"
tags:
  - docencia/prompt
  - docencia/estandard
  - obsidian/guia
---

# 📋 Estàndard i Directrius per al Disseny de Sessions (Prompt Màster)

Aquest document estableix la **plantilla, estructura i criteris obligatoris** per redactar i mantenir totes les sessions de classe del Mòdul 5023 (**Posada en producció segura**) en aquest Vault d'Obsidian.

> [!IMPORTANT]
> **Instrucció per a l'assistent d'IA**:  
> Quan l'usuari demani crear, ampliar o actualitzar sessions (per exemple, les sessions 06 a 50) fent referència a aquest fitxer, **has de seguir fil per randa l'estructura de 9 seccions, els paràmetres de calendari i les regles de format aquí definides sense saltar-te cap apartat**.

---

## ⚙️ 1. Paràmetres Operatius del Curs

1. **Durada de cada classe**: Exactament **2 hores (120 minuts reals)**.
2. **Cadència setmanal**: **2 dies per setmana: DILLUNS i DIVENDRES** (4 hores totals/setmana).
3. **Punt de partida del curs**:
   * Sessió 01: Divendres, 18/09/2026.
   * Sessió 02: Dilluns, 21/09/2026.
   * Sessió 03: Divendres, 25/09/2026.
   * Sessió 04: Dilluns, 28/09/2026.
   * Sessió 05: Divendres, 02/10/2026 (i així successivament fins a 50 sessions).
4. **Format tècnic**:
   * **100% Markdown pur**.
   * **PROHIBIT l'ús de Dataview** o plugins externs (l'únic plugin permès al Vault és el Kanban per als entregables).
   * **PROHIBIT l'ús de LaTeX mal formatat** (com `$ \rightarrow $` o `\times`). Utilitzar sempre caràcters Unicode nets com `→` i mides com `800 × 500 px`.

---

## 🏛️ 2. Estructura Obligatòria de cada Document de Sessió (`02_Sessions/`)

Cada sessió ha de contenir exactament les següents **9 seccions**:

### Frontmatter YAML
```yaml
---
tipus: sessio
numero: <NUMERO>
setmana: <SETMANA>
dia_setmana: "<Dilluns | Divendres>"
sessio_setmana: "<1 de 2 | 2 de 2>"
titol: "<TÍTOL DESCRIPTIU>"
data: YYYY-MM-DD
hores: 2
durada_min: 120
bloc: "<01_Desenvolupament_Web | 02_Hacking_Web | 03_Hacking_Mobil | 04_Desplegament_Segur>"
ra:
  - "<RA1 | RA2 | RA3 | RA4 | RA5>"
estat: "<Pendent | En curs | Impartida>"
apunts_a_ensenyar_avui:
  - "[[Ruta_a_la_nota_teorica_1|Títol 1]]"
  - "[[Ruta_a_la_nota_teorica_2|Títol 2]]"
codi_exemple_a_ensenyar: [] # Rutes a carpetes o fitxers de codi d'exemple si escau
labs_associats:
  - "[[Ruta_al_laboratori|Nom Lab]]"
projecte_associat: [] # Enllaç a fites si s'avança el projecte
tags:
  - docencia/sessio
  - setmana/<XX>
  - ra/<raX>
---
```

### Secció 1: 📖 Apunts Originals del Temari a Projectar i Explicar Avui
* **Obligatori**: Enllaços explícits amb format `[[01_Temari/...]]` als fitxers d'apunts originals copiats al repositori.
* **Per a cada fitxer d'apunts**:
  - Especificar els minuts concrets en què s'ha d'obrir al proyector (ex: *Minuts 15 a 35*).
  - Llistar els **epígrafs o apartats exactes** del fitxer que el professor ha d'ensenyar.
  - Destacar la **relevància per a la ciberseguretat** d'aquell contingut (per què importa, què s'explotarà al Bloc 2).

### Secció 2: ⏱️ Cronograma Minut a Minut (120 minuts reals)
* Taula resum amb les fases de la sessió:
  1. `00:00 - 00:15`: Repàs, resolució de dubtes i pregunta disparadora (*warm-up*).
  2. `00:15 - 00:45`: Projecció d'apunts i *Live Coding* del docent (demostració en pantalla).
  3. `00:45 - 01:35`: Laboratori pràctic dels alumnes (50 min) amb **3 Checkpoints obligatoris** (als 20 min, 35 min i 50 min de pràctica) per monitorar el ritme de les taules.
  4. `01:35 - 01:50`: Eines de depuració (DevTools F12, logs, terminal) i anàlisi d'errors comuns.
  5. `01:50 - 02:00`: Posada en comú, preguntes de control (*Exit Ticket*) i tancament.

### Secció 3: 🖼️ Esquemes per a la Pissarra (Whiteboard)
* Diagrama visual clar (en format caixa de text ASCII o Mermaid) que el professor pugui dibuixar ràpidament amb retolador per explicar la lògica de dades o el flux de peticions.

### Secció 4: 💻 Guió de Live Coding del Docent
* Fragments de codi reals, complets, nets i funcionals que el professor escriu o projecta pas a pas.

### Secció 5: 🧪 Treball Pràctic dels Alumnes (Laboratori)
* Enllaç al fitxer de laboratori a `03_Exercicis_i_Labs/Enunciats/`.
* Explicació de les tasques que els alumnes han de resoldre a classe en aquesta sessió.

### Secció 6: ❓ Preguntes de Control Conceptual
* Entre 2 i 3 preguntes socràtiques per fer als alumnes amb:
  - **Pregunta formulada**.
  - **Resposta tècnica esperada (10/10)**.
  - **Error conceptual típic de l'alumne**.

### Secció 7: ⚠️ Troubleshooting a l'Aula (Solucions en 30 segons)
* Taula amb mínim 3 incidències tècniques comunes a l'aula d'informàtica:
  - Columna 1: *Símptoma a la pantalla de l'alumne*.
  - Columna 2: *Causa real*.
  - Columna 3: *Solució immediata en 30 segons (comanda o acció)*.

### Secció 8: 📝 Tancament, Entregables i Connexió
* Recordatori dels lliuraments pendents (amb dates límit sincronitzades amb el Tauler Kanban).
* Enllaç i continuïtat amb la **següent classe (Dilluns o Divendres)**.

### Secció 9: 🧑‍🏫 Codi Màster de Referència per al Docent
* Codi complet o script final de la sessió perquè el professor el pugui consultar o facilitar si algun alumne es bloqueja de forma irrecuperable.
