## Why

Prowadzący chcą mieć prezentację jako plik PDF, który można zapisać, wysłać uczestnikom lub otworzyć bez aplikacji. Dziś slajdy można oglądać tylko w przeglądarce.

## What Changes

- W widoku prezentacji pojawia się przycisk „Eksportuj do PDF”.
- Przycisk otwiera okno drukowania przeglądarki z układem „1 slajd = 1 strona” w proporcjach 16:9, z zachowaniem kolorów motywu. Użytkownik wybiera „Zapisz jako PDF” i zapisuje plik na dysku.
- Nazwa pliku proponowana przez przeglądarkę pochodzi z tytułu prezentacji.
- Eksport obejmuje wszystkie slajdy, niezależnie od tego, który jest aktualnie wyświetlany, i nie dodaje elementów interfejsu (miniatur, przycisków, notatek).
- Bez nowych bibliotek i bez kroku budowania. Brak zmian łamiących.
- Aktualizacja dokumentacji użytkownika `cheatsheet/docs/prezentacje.md`.

## Capabilities

### New Capabilities
- `presentation-pdf-export`: eksport całej prezentacji do PDF (układ stron, kolory, nazwa pliku).

### Modified Capabilities
- `presentation-viewer`: pasek sterowania viewera dostaje przycisk eksportu.

## Impact

- `cheatsheet/index.html` (przycisk w viewerze, budowa kontenera do druku, style `@media print` i `@page`, TypeScript).
- `cheatsheet/docs/prezentacje.md` (nowa sekcja o eksporcie do PDF).
- `cheatsheet/README.md` (jeśli opisuje funkcje viewera).
- Brak nowych zależności ani zmian w Dockerze i w schemacie JSON.
