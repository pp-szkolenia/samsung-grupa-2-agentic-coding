## Why

Edytor i viewer prezentacji są dziś bardzo proste: każdy slajd to tytuł, lista punktów, kod i notatki, bez wyboru układu i bez stylowania. Prowadzący potrzebują narzędzia zbliżonego do profesjonalnych edytorów prezentacji, żeby tworzyć zróżnicowane i estetyczne slajdy.

## What Changes

- Slajdy dostają pole `type` z 6 typami: `title` (tytułowy), `text` (tekst), `bullets` (wypunktowana lista), `two-columns` (dwie kolumny), `quote` (cytat), `code` (kod). Każdy typ ma własne pola i własny układ.
- Prezentacja dostaje sekcję `theme`: kolor akcentu, kolor tła, kolor tekstu i krój pisma (np. sans-serif, serif, monospace, display).
- Edytor: wybór typu slajdu, pola zależne od typu, wybór motywu, dodawanie/usuwanie/duplikowanie/zmiana kolejności slajdów oraz podgląd slajdu na żywo obok formularza.
- Viewer: panel z miniaturami slajdów, podgląd następnego slajdu, pasek postępu, tryb prezentera (aktualny slajd, następny slajd, notatki), pełny ekran i skróty klawiszowe.
- Istniejące prezentacje bez `type` i `theme` nadal działają (slajd z `bullets`/`code` jest traktowany jak dotychczas, motyw domyślny). Brak zmian łamiących.
- Aktualizacja przykładowych prezentacji, schematu `presentation.schema.json` i dokumentacji w `cheatsheet/docs/prezentacje.md` oraz `edytor.md`.

## Capabilities

### New Capabilities
- `slide-types`: typy slajdów, ich pola i układy oraz zgodność wsteczna ze starym formatem.
- `slide-styling`: motyw prezentacji (kolory i krój pisma) zapisywany w dokumencie.
- `presentation-viewer`: rozbudowany viewer (miniatury, podgląd następnego slajdu, tryb prezentera, skróty) i podgląd na żywo w edytorze.

### Modified Capabilities
<!-- brak istniejących specyfikacji w openspec/specs/ -->

## Impact

- `cheatsheet/index.html` (render slajdów, viewer, edytor, style CSS, TypeScript).
- `cheatsheet/schemas/presentation.schema.json` (nowe pola `type`, `theme`, pola typów).
- Edytor jest generowany ze schematu, więc potrzebuje obsługi pól warunkowych (zależnych od typu) i pól wyboru/koloru.
- `cheatsheet/examples/presentations/*.json` (użycie nowych typów).
- `cheatsheet/docs/` (artykuły użytkownika), `DESIGN.md` (zgodność wyglądu).
- Brak nowych zależności ani kroku budowania.
