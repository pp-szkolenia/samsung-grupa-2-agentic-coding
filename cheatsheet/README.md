# Ściąga Claude Code

## Uruchomienie w Dockerze

Wymagany jest Docker z wtyczką Compose. Z katalogu `cheatsheet/` uruchom:

```bash
docker compose up --build
```

Następnie otwórz w przeglądarce: http://localhost:8080

Katalog `cheatsheet/` jest podmontowany do kontenera jako wolumen, więc zmiany w plikach są widoczne po odświeżeniu strony, bez ponownego budowania i restartu kontenera.

Zatrzymanie: `Ctrl+C`, a potem `docker compose down`.

## Dokumenty

Strona główna to lista dokumentów. Są dwa rodzaje:

- **Ściąga** – sekcje z komendami, z wyszukiwaniem i filtrami (jak wbudowana ściąga).
- **Prezentacja** – slajdy z tytułem, punktami, kodem i notatkami; przełączanie strzałkami `←` / `→`, przycisk „Pełny ekran”.

Nowy dokument tworzysz przyciskiem „Nowa ściąga” lub „Nowa prezentacja”. Formularz generuje się ze schematu JSON, a po prawej stronie na bieżąco widać wynikowy JSON. Błędy względem schematu są wypisywane przed zapisem.

Schematy leżą w `cheatsheet/schemas/`:

- `cheatsheet.schema.json`
- `presentation.schema.json`

Wbudowana ściąga (`claude-code-commands.json`) jest tylko do odczytu – żeby ją edytować, użyj „Duplikuj”.

Własne dokumenty zapisują się w `localStorage` przeglądarki (klucz `cheatsheet.documents`), więc są widoczne tylko w tej przeglądarce. Aby dodać dokument do repozytorium, pobierz go przyciskiem „Pobierz JSON” i zapisz w `cheatsheet/`.

## Uruchomienie bez Dockera

Z katalogu `cheatsheet/`:

```bash
python3 -m http.server 8080
```

Następnie otwórz w przeglądarce: http://localhost:8080
