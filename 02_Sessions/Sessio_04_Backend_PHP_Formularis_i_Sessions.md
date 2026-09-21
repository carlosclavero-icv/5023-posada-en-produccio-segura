---
tipus: sessio
numero: 4
setmana: 2
dia_setmana: "Dilluns"
sessio_setmana: "2 de 2"
titol: "Backend PHP: Captura Segura de Formularis, Cookies i Gestió de Sessions"
data: 2026-09-28
hores: 2
durada_min: 120
bloc: "01_Desenvolupament_Web"
ra:
  - "RA1"
estat: "Pendent"
apunts_a_ensenyar_avui:
  - "[[01_Temari/01_Desenvolupament_Web/03_BACKEND/01_formularis_dades|01. Processament de Formularis en PHP]]"
  - "[[01_Temari/01_Desenvolupament_Web/03_BACKEND/02_cookies_sessions|02. Cookies i Gestió de Sessions]]"
codi_exemple_a_ensenyar:
  - "[[01_Temari/01_Desenvolupament_Web/03_BACKEND/01_formularis|Carpeta d'Exemple: 01_formularis]]"
  - "[[01_Temari/01_Desenvolupament_Web/03_BACKEND/02_cookies_sessions|Carpeta d'Exemple: 02_cookies_sessions]]"
labs_associats:
  - "[[03_Exercicis_i_Labs/Enunciats/LAB_02_Interactivitat_DOM_Joc|LAB-02: Recordatori lliurament divendres]]"
  - "[[03_Exercicis_i_Labs/Enunciats/LAB_03_CRUD_PHP_MySQL|LAB_03: Backend PHP i Sessions (Part 1)]]"
projecte_associat:
  - "[[04_Projecte_Videojocs/00_Index_Projecte|Projecte Plataforma de Videojocs]]"
tags:
  - docencia/sessio
  - setmana/02
  - ra/ra1
  - stack/php
---

# 🛡️ Sessió 04: Backend PHP: Formularis Segurs, Cookies i Sessions

> [!NOTE]
> **Data**: Dilluns, 28 de setembre de 2026 (Classe 2 de 2 de la Setmana 2) | **Durada**: 120 minuts (2 hores)  
> **Resultat d'Aprenentatge**: [[00_Meta/🎯 Mapeig_RAs_i_Criteris#RA1|RA1 - Cicle d'execució en servidor, gestió de formularis i seguretat de sessions]]  
> ⏰ **Lliurament del LAB-02**: Recordar que LAB-02 (Joc JS) venç el proper divendres 02/10/2026.

---

## 📖 1. Apunts Originals del Temari a Projectar i Explicar Avui

A la carpeta `01_Temari/01_Desenvolupament_Web/03_BACKEND/` hi ha els apunts oficials. **Avui has de projectar i explicar aquestes 2 notes**:

### 📄 1.1 [[01_Temari/01_Desenvolupament_Web/03_BACKEND/01_formularis_dades|01_formularis_dades.md]] (Projectar min 15 a 35)
* **Apartats concrets a ensenyar al proyector**:
  1. **"Mètodes de transmissió: GET vs POST"**:
     - *GET*: Envia paràmetres com a Query String a la URL. Visible a la barra d'adreces, desat a l'historial del navegador i als logs d'Apache (`/var/log/apache2/access.log`). **Mai utilitzar GET per a dades sensibles o contrasenyes**.
     - *POST*: Envia les dades al cos (*body*) de la petició HTTP. No queda registrat a les URLs.
  2. **"Variables Superglobals (`$_GET`, `$_POST`, `$_SERVER`)"**:
     - Com PHP parseja automàticament les peticions entrants en arrays associatius.
     - Comprovar el mètode d'enviament amb `if ($_SERVER['REQUEST_METHOD'] === 'POST')`.
  3. **"Sanitització preventiva contra XSS"**:
     - Mostrar l'ús de `htmlspecialchars(trim($_POST['nom_usuari']))` per neutralitzar caràcters perillosos com `<`, `>`, `"`, `'`.
     - Mostrar la validació d'emails amb `filter_var($_POST['email'], FILTER_VALIDATE_EMAIL)`.

### 📄 1.2 [[01_Temari/01_Desenvolupament_Web/03_BACKEND/02_cookies_sessions|02_cookies_sessions.md]] (Projectar min 35 a 55)
* **Apartats concrets a ensenyar al proyector**:
  1. **"El Protocol HTTP és Stateless (Sense Estat)"**:
     - Per què el servidor no sap qui ets entre una petició i la següent.
     - La solució: la **Cookie de Sessió** com a identificador temporal.
  2. **"Cicle de Vida de la Sessió en PHP"**:
     - Com `session_start()` cerca la cookie `PHPSESSID`. Si no existeix, genera un identificador aleatori criptogràfic i crea un fitxer a `/var/lib/php/sessions/sess_<ID>`.
  3. **"Flags de Seguretat Crítics a les Cookies" (Clau per a Ciberseguretat)**:
     - `HttpOnly`: Impedeix que JavaScript accedeixi a la cookie amb `document.cookie` (bloqueja el robatori de sessió per atacs XSS).
     - `SameSite=Strict`: Impedeix que la cookie s'enviï en peticions creuades (mitiga atacs CSRF).
     - `session_regenerate_id(true)`: Genera un nou ID de sessió just en fer login per evitar atacs de *Session Fixation*.
  4. **"Tancament de Sessió Segur (`logout.php`)"**:
     - Buidar l'array `$_SESSION = []`, destruir la cookie al client amb `setcookie()` i eliminar el fitxer del servidor amb `session_destroy()`.

---

## ⏱️ 2. Cronograma Minut a Minut (120 minuts)

```
┌─────────────┬─────────────────────────────────────────────────────────────────┐
│ Minuts      │ Activitat a l'Aula (Dilluns 28/09/2026)                         │
├─────────────┼─────────────────────────────────────────────────────────────────┤
│ 00:00-00:15 │ 1. Repàs i repte d'obertura: Com sap el web qui està jugant?   │
│ 00:15-00:35 │ 2. Projecció apunts 01_formularis_dades: GET, POST i seguretat │
│ 00:35-00:55 │ 3. Projecció apunts 02_cookies_sessions: PHPSESSID i flags      │
│ 00:55-01:45 │ 4. Laboratori guiat (LAB-03 Part 1): login, perfil i logout     │
│             │    • Min 80: Checkpoint 1 (login.html i processament POST segur)│
│             │    • Min 95: Checkpoint 2 (session_start i pàgina privada perfil│
│             │    • Min 115: Checkpoint 3 (logout complet i verificació cookies│
│ 01:45-01:55 │ 5. DevTools Storage: Comprovar flags HttpOnly des de la consola │
│ 01:55-02:00 │ 6. Tancament i connexió amb MariaDB per a Divendres 02/10       │
└─────────────┴─────────────────────────────────────────────────────────────────┘
```

---

## 🖼️ 3. Esquemes per a la Pissarra (Whiteboard)

```
[ NAVEGADOR CLIENT ]                                        [ SERVIDOR APACHE + PHP ]
         │                                                             │
         │──── 1. POST /login.php (user=admin, pass=secret) ──────────>│
         │                                                             │ Verifica credencials
         │                                                             │ session_start()
         │<─── 2. Set-Cookie: PHPSESSID=ab12cd34; HttpOnly; SameSite ──│ Desa fitxer a disc:
         │        Location: perfil.php (HTTP 302)                      │ /var/lib/php/sessions/
         │                                                             │ sess_ab12cd34
         │                                                             │
         │──── 3. GET /perfil.php (Cookie: PHPSESSID=ab12cd34) ───────>│
         │                                                             │ Llegeix sess_ab12cd34
         │                                                             │ $_SESSION['auth'] === true
         │<─── 4. Resposta 200 OK: "Benvingut admin al joc!" ──────────│
```

---

## 💻 4. Guió de Live Coding del Docent

Crea a `/var/www/html/auth/` els dos fitxers centrals:

### 1. `login.php` (Processament segur amb sessions configurades)
```php
<?php
// Configuració defensiva de la cookie abans d'iniciar sessió
session_start([
    'cookie_httponly' => true,  // Bloqueja accés des de JavaScript
    'cookie_samesite' => 'Strict' // Bloqueja peticions cross-site
]);

if ($_SERVER['REQUEST_METHOD'] !== 'POST') {
    header('Location: login.html');
    exit;
}

$usuari   = trim($_POST['username'] ?? '');
$password = trim($_POST['password'] ?? '');

// Comprovació temporal hardcoded (a la Sessió 05 anirà contra MariaDB)
if ($usuari === 'alumne' && $password === 'Vallbona2026!') {
    // CRÍTIC: Regenerar identificador per immunitzar contra Session Fixation
    session_regenerate_id(true);
    
    $_SESSION['autenticat'] = true;
    $_SESSION['usuari']     = $usuari;
    
    header('Location: perfil.php');
    exit; // SEMPRE exit després d'un header de redirecció!
} else {
    echo "<p style='color:red;'>Credencials no vàlides.</p>";
    echo "<a href='login.html'>Torna a intentar-ho</a>";
}
```

### 2. `perfil.php` (Pàgina protegida)
```php
<?php
session_start();

// Control d'Accés: Si no hi ha sessió vàlida, expulsem l'usuari
if (!isset($_SESSION['autenticat']) || $_SESSION['autenticat'] !== true) {
    header('Location: login.html?error=no_autoritzat');
    exit;
}

$nomNet = htmlspecialchars($_SESSION['usuari']);
?>
<!DOCTYPE html>
<html lang="ca">
<head>
    <meta charset="UTF-8">
    <title>Perfil del Jugador</title>
</head>
<body>
    <h1>Benvingut/da a la plataforma, <?= $nomNet ?>!</h1>
    <p>Tens accés als jocs de l'empresa.</p>
    <p><a href="../joc/index.html">Anar a jugar a Naus vs Ovnis</a></p>
    <hr>
    <a href="logout.php">Tancar la Sessió</a>
</body>
</html>
```

---

## 🧪 5. Treball Pràctic dels Alumnes (Minuts 55 a 105)

Els alumnes treballen la primera part del laboratori:
📄 [[03_Exercicis_i_Labs/Enunciats/LAB_03_CRUD_PHP_MySQL|LAB-03: Backend PHP, Sessions i CRUD MySQL]].

### Fites d'avui a les taules:
1. **Checkpoint 1 (min 80)**: Crear `login.html` amb mètode `POST` i camps `username` i `password`.
2. **Checkpoint 2 (min 95)**: Crear `login.php` i `perfil.php`. Comprovar que si intenten entrar directament a `http://localhost/auth/perfil.php` sense fer login, el servidor els redirigeix automàticament a `login.html`.
3. **Checkpoint 3 (min 115)**: Crear `logout.php`. Verificar que després de clicar logout, el botó "Enrere" del navegador ja no permet veure les dades privades.

---

## ❓ 6. Preguntes de Control Conceptual

1. **Pregunta**: *Per què és un error greu de seguretat fer `header('Location: login.html');` sense posar un `exit;` a la línia següent?*  
   → Perquè la funció `header()` només afegeix una capçalera HTTP a la cua de sortida, però l'intèrpret de PHP continua executant el codi que hi ha a sota. Si un atacant utilitza un client com `curl` que ignora redireccions automàtiques, rebrà i veurà tot el contingut privat de la pàgina.
2. **Pregunta**: *Si obrim la consola del navegador (F12) i executem `console.log(document.cookie)`, podrem veure la cookie `PHPSESSID` si hem activat el flag `HttpOnly`?*  
   → No. El navegador té instruccions estrictes d'ocultar aquesta cookie a qualsevol script de JavaScript per evitar robatoris de sessió en cas d'atacs XSS.

---

## ⚠️ 7. Troubleshooting a l'Aula (Solucions en 30 segons)

| Símptoma | Causa real | Solució en 30 segons |
| :--- | :--- | :--- |
| `Warning: Cannot modify header information - headers already sent by (output started at ...)` | Hi ha un espai en blanc, una línia buida o un `echo` abans de l'etiqueta `<?php` o abans de `header()`. | Les capçaleres HTTP s'han d'enviar abans que qualsevol byte de contingut. Eliminar espais en blanc abans de `<?php`. |
| La sessió es perd cada vegada que l'alumne canvia de pàgina. | S'ha oblidat incloure `session_start();` a l'inici d'algun dels fitxers PHP. | Afegir `session_start();` com a primera instrucció a tots els fitxers que llegeixin o modifiquin `$_SESSION`. |
| El formulari envia les dades però `$_POST` arriba buit. | L'etiqueta `<form>` no té l'atribut `method="POST"` (per defecte fa GET) o els inputs no tenen atribut `name=""`. | Comprovar que cada `<input>` té l'atribut `name="username"`, `name="password"`. |

---

## 📝 8. Tancament, Entregables i Connexió

* **Recordatori d'entregues**: Aquest **Divendres 02/10** és el darrer dia per entregar el **LAB-02 (Joc en JS)**.
* **Enllaç amb Divendres 02/10 (Sessió 05)**: Avui hem validat usuaris de forma simulada. Divendres connectarem PHP amb la nostra base de dades **MariaDB amb PDO**, aprendrem a aplicar consultes preparades contra injeccions SQL i crearem els primers endpoints de la nostra API REST en JSON.
