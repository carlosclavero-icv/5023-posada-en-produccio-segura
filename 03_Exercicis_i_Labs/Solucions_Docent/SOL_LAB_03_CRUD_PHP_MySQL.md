---
tipus: solucio_docent
codi: "SOL-LAB-03"
exercici_associat: "[[03_Exercicis_i_Labs/Enunciats/LAB_03_CRUD_PHP_MySQL|LAB-03]]"
bloc: "01_Desenvolupament_Web"
ra:
  - "RA1"
tags:
  - docencia/solucio
  - ra/ra1
---

# 🧑‍🏫 Guia de Correcció i Solució: LAB-03 (PHP, Sessions i MySQL)

## 🛡️ Checklist de Seguretat Obligatòria
En avaluar aquest laboratori, penalitzar immediatament si es detecta qualsevol d'aquests 3 errors crítics:
1. **Contrasenyes en text pla o amb `md5()`**: Obligatori ús de `password_hash($p, PASSWORD_BCRYPT)`.
2. **Consultes SQL amb concatenació de strings**: Obligatori `prepare()` + `execute()`.
3. **Manca d'`exit;` després de `header('Location: ...')`**.

---

## 💻 Codi Complet del Cicle d'Autenticació

### `logout.php` (Tancament Impecable de Sessió)
```php
<?php
session_start();

// 1. Buidar array de sessió en memòria
$_SESSION = [];

// 2. Destruir la cookie de sessió al navegador del client
if (ini_get("session.use_cookies")) {
    $params = session_get_cookie_params();
    setcookie(session_name(), '', time() - 42000,
        $params["path"], $params["domain"],
        $params["secure"], $params["httponly"]
    );
}

// 3. Destruir el fitxer de sessió al servidor
session_destroy();

header('Location: login.html?missatge=sessio_tancada');
exit;
```
