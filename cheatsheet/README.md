# Ściąga Claude Code

## Uruchomienie w Dockerze

Wymagany jest Docker z wtyczką Compose. Z katalogu `cheatsheet/` uruchom:

```bash
docker compose up --build
```

Następnie otwórz w przeglądarce: http://localhost:8080

Katalog `cheatsheet/` jest podmontowany do kontenera jako wolumen, więc zmiany w plikach są widoczne po odświeżeniu strony, bez ponownego budowania i restartu kontenera.

Zatrzymanie: `Ctrl+C`, a potem `docker compose down`.

## Uruchomienie bez Dockera

Z katalogu `cheatsheet/`:

```bash
python3 -m http.server 8080
```

Następnie otwórz w przeglądarce: http://localhost:8080
