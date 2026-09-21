---
tipus: sessio
numero: 5
setmana: 3
dia_setmana: "Divendres"
sessio_setmana: "1 de 2"
titol: "Bases de Dades amb MySQL/MariaDB (PDO), Consultes Preparades i API REST"
data: 2026-10-02
hores: 2
durada_min: 120
bloc: "01_Desenvolupament_Web"
ra:
  - "RA1"
estat: "Pendent"
apunts_a_ensenyar_avui:
  - "[[01_Temari/01_Desenvolupament_Web/03_BACKEND/03_bases_dades|03. Bases de Dades en PHP (PDO i Seguretat)]]"
  - "[[01_Temari/01_Desenvolupament_Web/03_BACKEND/04_api_rest|04. Desenvolupament d'API REST amb PHP]]"
codi_exemple_a_ensenyar:
  - "[[01_Temari/01_Desenvolupament_Web/03_BACKEND/03_bbdd|Carpeta d'Exemple: 03_bbdd (db_mysqli.php, script.sql)]]"
  - "[[01_Temari/01_Desenvolupament_Web/03_BACKEND/04_api|Carpeta d'Exemple: 04_api (db_pdo.php, api_basica.php)]]"
labs_associats:
  - "[[03_Exercicis_i_Labs/Enunciats/LAB_02_Interactivitat_DOM_Joc|LAB-02: Lliurament Avui (Data Límit)]]"
  - "[[03_Exercicis_i_Labs/Enunciats/LAB_03_CRUD_PHP_MySQL|LAB_03: CRUD PHP i MySQL (Part 2 - BBDD i API)]]"
projecte_associat:
  - "[[04_Projecte_Videojocs/00_Index_Projecte|Projecte Plataforma de Videojocs]]"
  - "[[00_Meta/📋 Tauler_Kanban_Entregables|Tauler Kanban]]"
tags:
  - docencia/sessio
  - setmana/03
  - ra/ra1
  - stack/php
  - stack/mysql
---

# 🗄️ Sessió 05: Bases de Dades amb PDO, Consultes Preparades i API REST

> [!NOTE]
> **Data**: Divendres, 02 d'octubre de 2026 (Classe 1 de 2 de la Setmana 3) | **Durada**: 120 minuts (2 hores)  
> **Resultat d'Aprenentatge**: [[00_Meta/🎯 Mapeig_RAs_i_Criteris#RA1|RA1 - Persistència de dades, creació d'APIs i prevenció de fallades d'injecció]]  
> 📥 **Recollida d'evidències**: Avui finalitza el termini del [[03_Exercicis_i_Labs/Enunciats/LAB_02_Interactivitat_DOM_Joc|LAB-02 (DOM i Videojoc JS)]].

---

## 📖 1. Apunts Originals del Temari a Projectar i Explicar Avui

A la carpeta `01_Temari/01_Desenvolupament_Web/03_BACKEND/` hi ha els apunts de referència. **Avui has de projectar i explicar aquestes 2 notes**:

### 📄 1.1 [[01_Temari/01_Desenvolupament_Web/03_BACKEND/03_bases_dades|03_bases_dades.md]] (Projectar min 15 a 40)
* **Apartats concrets a ensenyar al proyector**:
  1. **"Connexió a la Base de Dades: Per què usem PDO?"**:
     - Explicar la sintaxi de connexió amb DSN: `new PDO("mysql:host=127.0.0.1;dbname=...;charset=utf8mb4", ...)`.
     - Mostrar la gestió robusta d'errors amb blocs `try { ... } catch (PDOException $e) { ... }`.
     - Activar l'opció `PDO::ATTR_ERRMODE => PDO::ERRMODE_EXCEPTION`.
  2. **"La Regla d'Or contra Injeccions SQL: Sentències Preparades (*Prepared Statements*)"**:
     - **Crític per a Ciberseguretat**: Projectar l'exemple de codi vulnerable per concatenació (`"WHERE u = '$nom'"`).
     - Mostrar com es resol amb sentències preparades:
       - Pas 1: `$stmt = $pdo->prepare("SELECT * FROM usuaris WHERE nom_usuari = :nom");`
       - Pas 2: `$stmt->execute(['nom' => $nom]);`
     - Explicar als alumnes que la sentència preparada compila l'estructura de la consulta al motor de la BBDD abans de rebre les dades, fent impossible que una cometa `'` alteri la lògica.
  3. **"Emmagatzematge Segur de Contrasenyes (Hashing amb Bcrypt)"**:
     - Per què desar contrasenyes en text pla o amb `md5()` és una negligència greu.
     - Ús de `password_hash($password, PASSWORD_BCRYPT)` i verificació amb `password_verify($password, $hash)`.

### 📄 1.2 [[01_Temari/01_Desenvolupament_Web/03_BACKEND/04_api_rest|04_api_rest.md]] (Projectar min 40 a 60)
* **Apartats concrets a ensenyar al proyector**:
  1. **"Què és una API REST?"**:
     - Comunicació desacoblada entre el Frontend (JavaScript) i el Backend (PHP) intercanviant exclusivament missatges JSON.
  2. **"Capçaleres HTTP de Resposta"**:
     - `header('Content-Type: application/json; charset=utf-8');`.
     - Ús de codis d'estat HTTP: `200` (OK), `201` (Creat), `400` (Petició incorrecta), `401` (No autoritzat), `404` (No trobat), `500` (Error intern).
  3. **"Recepció de Dades JSON en Petició POST"**:
     - Explicar per què `$_POST` arriba buit quan s'envia un JSON des de JavaScript `fetch()`.
     - Mostrar com llegir el flux d'entrada brut: `file_get_contents('php://input')` seguit de `json_decode()`.
  4. **"Emissió de Respostes JSON"**:
     - `echo json_encode($dades, JSON_PRETTY_PRINT | JSON_UNESCAPED_UNICODE);`.

---

## ⏱️ 2. Cronograma Minut a Minut (120 minuts)

```
┌─────────────┬─────────────────────────────────────────────────────────────────┐
│ Minuts      │ Activitat a l'Aula (Divendres 02/10/2026)                       │
├─────────────┼─────────────────────────────────────────────────────────────────┤
│ 00:00-00:15 │ 1. Repàs i recollida del LAB-02 (comprovació de lliuraments)    │
│ 00:15-00:40 │ 2. Projecció apunts 03_bases_dades: PDO, Prepared Statements    │
│ 00:40-01:00 │ 3. Projecció apunts 04_api_rest: Endpoints i respostes JSON     │
│ 01:00-01:45 │ 4. Pràctica guiada (LAB-03 Part 2): db.php, taules i api/jocs   │
│             │    • Min 75: Checkpoint 1 (Script SQL i connexió PDO db.php)    │
│             │    • Min 95: Checkpoint 2 (Registre amb password_hash Bcrypt)   │
│             │    • Min 115: Checkpoint 3 (Endpoint GET /api/jocs.php en JSON) │
│ 01:45-01:55 │ 5. Proves d'API des de la terminal amb curl i extensió Thunder  │
│ 01:55-02:00 │ 6. Tancament i connexió amb la Sessió 06 (Arquitectura MVC)     │
└─────────────┴─────────────────────────────────────────────────────────────────┘
```

---

## 🖼️ 3. Esquemes per a la Pissarra (Whiteboard)

```
INJECCIÓ SQL (Vulnerable per concatenació):
  $sql = "SELECT * FROM usuaris WHERE u = '" . $_POST['u'] . "'";
  Input de l'atacant: admin' OR '1'='1
  Consulta executada: SELECT * FROM usuaris WHERE u = 'admin' OR '1'='1'  <-- Bypass total!

SENTÈNCIA PREPARADA (Segura amb PDO):
  Pass 1 (Estructura): PREPARE "SELECT * FROM usuaris WHERE nom_usuari = :u"
  Pass 2 (Dades):      EXECUTE with :u = "admin' OR '1'='1"
  Resultat: El motor busca un usuari anomenat literalment "admin' OR '1'='1". Injecció impossible!
```

---

## 💻 4. Guió de Live Coding del Docent

### 1. `config/db.php` (Connexió PDO indestructible)
```php
<?php
$host = '127.0.0.1';
$db   = 'plataforma_jocs';
$user = 'ciber_user';
$pass = 'CiberPass2026!';
$charset = 'utf8mb4';

$dsn = "mysql:host=$host;dbname=$db;charset=$charset";
$options = [
    PDO::ATTR_ERRMODE            => PDO::ERRMODE_EXCEPTION, // Llança excepcions en cas d'error
    PDO::ATTR_DEFAULT_FETCH_MODE => PDO::FETCH_ASSOC,       // Arrays associatius nets
    PDO::ATTR_EMULATE_PREPARES   => false,                  // Prepared Statements reals al motor
];

try {
    $pdo = new PDO($dsn, $user, $pass, $options);
} catch (PDOException $e) {
    // Mai mostrar $e->getMessage() a l'usuari final!
    error_log($e->getMessage());
    die("Error intern de base de dades.");
}
```

### 2. `api/jocs.php` (Primer endpoint REST en JSON)
```php
<?php
header('Content-Type: application/json; charset=utf-8');
require_once '../config/db.php';

// Endpoint públic: GET /api/jocs.php
if ($_SERVER['REQUEST_METHOD'] === 'GET') {
    $stmt = $pdo->query("SELECT id, nom, descripcio, nivells_totals FROM jocs WHERE actiu = 1");
    $jocs = $stmt->fetchAll();
    
    http_response_code(200);
    echo json_encode([
        'status' => 'success',
        'data'   => $jocs
    ], JSON_PRETTY_PRINT | JSON_UNESCAPED_UNICODE);
    exit;
}

http_response_code(405); // Method Not Allowed
echo json_encode(['status' => 'error', 'message' => 'Mètode no permès']);
```

---

## 🧪 5. Treball Pràctic dels Alumnes (Minuts 60 a 105)

Els alumnes completen la segona part del laboratori:
📄 [[03_Exercicis_i_Labs/Enunciats/LAB_03_CRUD_PHP_MySQL|LAB-03: Backend PHP, Sessions i CRUD MySQL]].

### Fites d'avui a les taules:
1. **Checkpoint 1 (min 75)**: Crear la base de dades `plataforma_jocs` a MariaDB amb les taules `usuaris` i `jocs`, i comprovar la connexió de `config/db.php`.
2. **Checkpoint 2 (min 95)**: Registrar un usuari i fer `SELECT * FROM usuaris;` des de la terminal per verificar que la contrasenya és un hash Bcrypt de 60 caràcters (`$2y$10$...`).
3. **Checkpoint 3 (min 115)**: Crear l'endpoint `api/jocs.php` i consultar-lo des del navegador o `curl` obtenint un JSON perfectament formatat.

---

## ❓ 6. Preguntes de Control Conceptual

1. **Pregunta**: *Per què activem `PDO::ATTR_EMULATE_PREPARES => false` a les opcions de PDO?*  
   → Perquè obliga PHP a delegar la compilació de la sentència preparada al motor MariaDB en lloc d'emular-la internament amb reemplaçaments de strings. Això garanteix protecció total contra injeccions SQL complexes.
2. **Pregunta**: *Si enviem un JSON des de JavaScript amb `fetch('/api/guardar', { method: 'POST', body: JSON.stringify(dades) })`, per què la variable `$_POST` de PHP arriba completament buida?*  
   → Perquè `$_POST` només sap parsejar peticions amb format formulari (`application/x-www-form-urlencoded` o `multipart/form-data`). Quan enviem `application/json`, cal llegir el cos en cru amb `file_get_contents('php://input')` i parsejar-lo amb `json_decode()`.

---

## ⚠️ 7. Troubleshooting a l'Aula (Solucions en 30 segons)

| Símptoma | Causa real | Solució en 30 segons |
| :--- | :--- | :--- |
| `SQLSTATE[HY000] [1045] Access denied for user 'ciber_user'@'localhost'` | L'usuari no té permisos creats a MariaDB per a la base de dades. | Obrir terminal: `sudo mysql` i executar: `GRANT ALL PRIVILEGES ON plataforma_jocs.* TO 'ciber_user'@'localhost' IDENTIFIED BY 'CiberPass2026!'; FLUSH PRIVILEGES;`. |
| La sortida de l'API JSON té caràcters d'accent o ce trencada trencats (`é`). | S'ha oblidat la bandera `JSON_UNESCAPED_UNICODE` a `json_encode()`. | Afegir les opcions: `json_encode($data, JSON_UNESCAPED_UNICODE | JSON_PRETTY_PRINT);`. |
| La consulta SQL falla però no apareix cap missatge d'error (pàgina en blanc). | S'ha capturat l'excepció amb un bloc `catch` buit o no s'ha activat `PDO::ERRMODE_EXCEPTION`. | Dins del `catch (PDOException $e)`, afegir temporalment `die($e->getMessage());` durant la fase de desenvolupament a l'aula. |

---

## 📝 8. Tancament, Entregables i Connexió

* **Estat d'entregues**: Avui recollim el **LAB-02 (Joc en JS)**.
* **Propera entrega**: El **LAB-03 (CRUD PHP i MySQL)** es lliurarà el proper **Divendres 16/10/2026** (inici de la Sessió 07).
* **Enllaç amb Dilluns 05/10 (Sessió 06)**: Ja tenim Frontend, Backend i Base de Dades. Dilluns aprendrem a estructurar aquest codi de forma professional utilitzant el **Patró Model-Vista-Controlador (MVC)** i un encaminador de rutes (`Router.php`).

---

## 🧑‍🏫 9. Codi Màster de Referència per al Docent

Si un alumne necessita el codi de referència de la connexió segura o d'inserció amb PDO, pots consultar directament:
📂 `01_Temari/01_Desenvolupament_Web/03_BACKEND/03_bbdd/db_mysqli.php` i `04_api/db_pdo.php`.
