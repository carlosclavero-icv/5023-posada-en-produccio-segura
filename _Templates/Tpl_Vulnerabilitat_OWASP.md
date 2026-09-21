---
tipus: vulnerabilitat
categoria_owasp: "A03:2021-Injection"
cwe: "CWE-89"
severitat_cvss: "High (8.5)"
ra:
  - "RA2"
  - "RA3"
tags:
  - seguretat/vulnerabilitat
  - owasp/top10
  - ra/ra3
---

# 🛡️ {{title}}

> **Categoria OWASP**: `A03:2021` | **CWE**: `CWE-89` | **Risc**: Alta

---

## 1. Descripció de la Fallada
Definició concisa de la vulnerabilitat i el seu impacte sobre la confidencialitat, integritat o disponibilitat.

---

## 2. Vector d'Atac i Explotació
Com descobreix i explota un atacant aquest punt feble.

### Exemple de Codi Vulnerable
```php
// Codi vulnerable
$id = $_GET['id'];
$query = "SELECT * FROM usuaris WHERE id = " . $id;
```

### Vector d'Atac (Payload)
```sql
1 OR 1=1 --
```

---

## 3. Mesures de Mitigació i Codi Segur
Com s'ha de solucionar en el cicle de desenvolupament segur.

### Exemple de Codi Corregit
```php
// Codi segur amb consultes preparades
$stmt = $pdo->prepare("SELECT * FROM usuaris WHERE id = :id");
$stmt->execute(['id' => $_GET['id']]);
```

---

## 🔗 Pràctiques Relacionades
- [[03_Exercicis_i_Labs/Enunciats/LAB_05_SQLi_DVWA|Laboratori Pràctic]]
