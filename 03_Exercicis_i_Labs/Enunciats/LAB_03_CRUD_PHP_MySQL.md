---
tipus: exercici
codi: "LAB-03"
titol: "Backend PHP: Sessions Segures i CRUD amb MySQL (PDO)"
bloc: "01_Desenvolupament_Web"
ra:
  - "RA1"
dificultat: "Mitjana"
entorn_requerit: "Servidor LAMP (Debian 12)"
avaluable: true
pes_nota: "5%"
temps_estimat_min: 120
tags:
  - docencia/exercici
  - ra/ra1
  - stack/php
  - stack/mysql
---

# 🧪 LAB-03: Backend PHP: Sessions Segures i CRUD amb MySQL (PDO)

> **Codi**: `LAB-03` | **Mòdul**: 5023 | **Durada**: 120 minuts | **Qualificació**: Avaluable (5%)

---

## 🎯 Objectius
* Crear una base de dades relacional i connectar-hi PHP mitjançant la classe `PDO`.
* Implementar un sistema complet de registre, autenticació i tancament de sessió amb cookies segures.
* Aplicar sentències preparades (*Prepared Statements*) en totes les operacions amb la base de dades.

---

## 📋 Tasques Pas a Pas

### Tasca 1: Model de Base de Dades
Accedeix a MariaDB i crea la base de dades i la taula d'usuaris:
```sql
CREATE DATABASE plataforma_jocs CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
USE plataforma_jocs;

CREATE TABLE usuaris (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nom_usuari VARCHAR(50) NOT NULL UNIQUE,
    email VARCHAR(100) NOT NULL UNIQUE,
    password_hash VARCHAR(255) NOT NULL,
    creat_el TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

### Tasca 2: Connexió PDO Segura (`db.php`)
Crea un fitxer de connexió que utilitzi blocs `try-catch` i activi el llançament d'excepcions en cas d'error.

### Tasca 3: Registre amb Xifratge de Contrasenyes (`registre.php`)
1. Valida que els camps no arribin buits i que l'email tingui un format correcte.
2. Hasheja la contrasenya amb la funció estàndard de PHP:
```php
$hash = password_hash($password, PASSWORD_BCRYPT);
```
3. Insereix l'usuari amb consultes preparades:
```php
$stmt = $pdo->prepare("INSERT INTO usuaris (nom_usuari, email, password_hash) VALUES (:nom, :email, :pass)");
$stmt->execute(['nom' => $nom, 'email' => $email, 'pass' => $hash]);
```

### Tasca 4: Autenticació i Gestió de Sessions (`login.php` i `perfil.php`)
1. Verifica les credencials amb `password_verify($password, $usuari['password_hash'])`.
2. Si és correcte, inicia sessió, regenera l'ID i desa les dades bàsiques:
```php
session_start([
    'cookie_httponly' => true,
    'cookie_samesite' => 'Strict'
]);
session_regenerate_id(true);
$_SESSION['user_id'] = $usuari['id'];
$_SESSION['username'] = $usuari['nom_usuari'];
```
3. A `perfil.php`, protegeix la pàgina verificant que `$_SESSION['user_id']` estigui definida. Si no ho està, redirigeix a `login.php`.

---

## 📤 Evidències a Lliurar
* Codi dels fitxers `db.php`, `registre.php`, `login.php` i `perfil.php`.
* Captura de la base de dades MariaDB mostrant la taula `usuaris` amb la contrasenya degudament xifrada (mai en text pla).
