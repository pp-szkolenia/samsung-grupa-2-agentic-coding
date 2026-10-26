# Instrukcje dla Claude

#### Przegląd projektu

Repozytorium powstało na szkolenie Coderslab (Samsung, grupa 2) o agentowym kodowaniu z Claude Code. Zawiera ściągę z komend, skrótów klawiszowych i plików konfiguracyjnych Claude Code, w katalogu `cheatsheet/`. Projekt jest dydaktyczny: ma być czytelny i prosty, bez zbędnej infrastruktury.

## Użytkownik końcowy

Odbiorcami są uczestnicy szkolenia, czyli osoby zaczynające pracę z Claude Code. Zakładają podstawową znajomość terminala i HTML, ale nie znają jeszcze pełnej składni komend i konfiguracji. Ściąga ma być szybka w przeglądaniu i wygodna do kopiowania komend.

## Stos technologiczny

- **Frontend:** czysty HTML, CSS i TypeScript w jednym pliku (`cheatsheet/index.html`), bez frameworków i bez kroku budowania.
- **Dane:** treść ściągi w pliku `cheatsheet/claude-code-commands.json` (sekcje z polami `command`, `description`, `example`, `tags`).
- **Uruchamianie lokalne:** w kontenerze Docker, uruchamiany z katalogu `cheatsheet/` poleceniem `docker compose up --build`; strona jest pod http://localhost:8080.
- **Dokumentacja:** `cheatsheet/README.md`, po polsku.

## Design
Wygląd strony powinien być zgodny z opisem w pliku DESIGN.md. Jeśli nie jest, to popraw to


## Git
Po każdej większej zmianie zrób commita w gicie

## OpenSpec

Gdy użytkownik proponuje większą zmianę w kodzie albo prosi o implementację czegoś większego niż krótkie zadanie, postępuj w tej kolejności:

1. **Propozycja:** automatycznie utwórz propozycję zmiany w OpenSpecu (skill `openspec-propose`). Nie zaczynaj implementacji.
2. **Akceptacja:** czekaj, aż użytkownik zaakceptuje propozycję. Implementację (skill `openspec-apply-change`) zaczynaj dopiero po akceptacji.
3. **Archiwizacja:** po zakończeniu implementacji zapytaj użytkownika, czy zmianę można już zarchiwizować (skill `openspec-archive-change`). Nie archiwizuj bez jego zgody.

Krótkie, drobne zadania (np. poprawka literówki, mała korekta stylu) nie wymagają propozycji w OpenSpecu.

## Dokumentacja użytkownika

Aplikacja ma instrukcję dla użytkownika w `cheatsheet/docs/` (widok `#/help`, lewy sidebar z artykułami). Po każdej zmianie widocznej dla użytkownika (nowa funkcja, zmienione zachowanie, usunięta opcja, nowy ekran) **musisz zaktualizować dokumentację** w tym samym commicie co zmiana. Do tego używaj skilla `user-docs`, który opisuje format artykułów, styl pisania i kroki aktualizacji. Nie pisz w `docs/` dokumentacji technicznej.

