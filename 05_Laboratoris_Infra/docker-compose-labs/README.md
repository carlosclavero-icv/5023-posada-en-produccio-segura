# Laboratoris de Pràctiques amb Docker

Aquest directori conté la configuració ràpida de Docker Compose per arrencar les plataformes de proves de seguretat de l'aula.

## Ports dels Serveis
* **DVWA**: [http://localhost:8081](http://localhost:8081)
  * Credencials per defecte: `admin` / `password`
  * Primera arrencada: Cal fer clic a **Create / Reset Database**.
* **OWASP Juice Shop**: [http://localhost:8082](http://localhost:8082)
* **bWAPP**: [http://localhost:8083/install.php](http://localhost:8083/install.php)
  * Primera arrencada: Fer clic a install per inicialitzar la base de dades.
  * Credencials: `bee` / `bug`

## Comandes de Gestió
```bash
# Arrencar tots els laboratoris en segon pla
docker compose up -d

# Veure l'estat dels contenidors
docker compose ps

# Aturar els laboratoris
docker compose down
```
