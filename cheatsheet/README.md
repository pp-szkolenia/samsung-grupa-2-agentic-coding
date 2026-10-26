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

Strona główna to lista dokumentów. Są trzy rodzaje:

- **Ściąga** – sekcje z komendami, z wyszukiwaniem i filtrami (jak wbudowana ściąga).
- **Prezentacja** – slajdy z tytułem, punktami, kodem i notatkami; przełączanie strzałkami `←` / `→`, przycisk „Pełny ekran”.
- **Quiz** – pytania z odpowiedziami; po wyborze od razu widać, czy odpowiedź jest poprawna, a na końcu wynik.

Nowy dokument tworzysz przyciskiem „Nowa ściąga”, „Nowa prezentacja” lub „Nowy quiz”. Formularz generuje się ze schematu JSON, a po prawej stronie na bieżąco widać wynikowy JSON. Błędy względem schematu są wypisywane przed zapisem.

Schematy leżą w `cheatsheet/schemas/`:

- `cheatsheet.schema.json`
- `presentation.schema.json`
- `quiz.schema.json`

Przy quizie pole „Poprawna odpowiedź” musi być dokładnie takie samo jak jedna z odpowiedzi. Schemat JSON tego nie sprawdza, więc literówka zostanie niezauważona.

Wbudowana ściąga (`claude-code-commands.json`) jest tylko do odczytu – żeby ją edytować, użyj „Duplikuj”.

Własne dokumenty zapisują się w `localStorage` przeglądarki (klucz `cheatsheet.documents`), więc są widoczne tylko w tej przeglądarce. Aby dodać dokument do repozytorium, pobierz go przyciskiem „Pobierz JSON” i zapisz w `cheatsheet/`.

### Przykłady

Katalog `cheatsheet/examples/` zawiera gotowe dokumenty (`presentations/`, `cheatsheets/` i `quizzes/`). Są tylko do odczytu, z etykietą „przykład”. Aby dodać nowy przykład, wystarczy zapisać plik `.json` w jednym z podkatalogów i odświeżyć stronę (albo wejść ponownie do biblioteki). Nie trzeba edytować kodu ani przebudowywać kontenera. Strona odczytuje listę plików z katalogu, więc działa to zarówno w Dockerze, jak i z `python3 -m http.server`.

## Instrukcja

Link „Instrukcja” w górnym pasku otwiera dokumentację użytkownika (http://localhost:8080/#/help). Artykuły są w `cheatsheet/docs/` jako pliki Markdown z nagłówkiem `title` i `order`. Lewy sidebar wypisuje je automatycznie, więc nowy plik pojawia się po odświeżeniu strony. Zasady pisania opisuje skill `user-docs` w `.claude/skills/user-docs/`.

## Uruchomienie bez Dockera

Z katalogu `cheatsheet/`:

```bash
python3 -m http.server 8080
```

Następnie otwórz w przeglądarce: http://localhost:8080
