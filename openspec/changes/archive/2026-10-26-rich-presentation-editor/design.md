## Context

Aplikacja to jeden plik `cheatsheet/index.html` (HTML, CSS, TypeScript) bez kroku budowania. Edytor jest generowany ze schematu JSON (`buildFields`, `cleanValue`, `validate`), a viewer renderuje slajd w `renderSlide`. Obecnie slajd ma tylko `title`, `bullets`, `code`, `notes`.

## Goals / Non-Goals

**Goals:** 6 typów slajdów, motyw (kolory, font), viewer z miniaturami, podglądem następnego slajdu i trybem prezentera, podgląd na żywo w edytorze, zgodność wsteczna.

**Non-Goals:** obrazy wgrywane z dysku, animacje i przejścia, edycja wizualna (drag and drop na slajdzie), współpraca wielu osób, eksport do PPTX.

## Decisions

- **Jedna funkcja `renderSlideContent(slide, theme)`** zwraca element slajdu dla każdego typu; używana przez viewer, miniatury, podgląd następnego slajdu i podgląd w edytorze. Miniatury to ten sam element skalowany przez CSS `transform: scale()` w kontenerze 16:9. Alternatywa (osobny render miniatur) odrzucona jako duplikacja.
- **Schemat: płaski slajd z polem `type` i polami opcjonalnymi** (`text`, `bullets`, `left`, `right`, `quote`, `author`, `code`, `language`). Zamiast `oneOf`, bo własny walidator i generator formularzy nie obsługują `oneOf`. Nowa adnotacja `x-showFor: [typy]` ukrywa pola nieistotne dla wybranego typu.
- **Nowe adnotacje schematu** `x-enum`/`enum` (lista wyboru), `x-format: "color"` (input koloru), obsługiwane w `buildFields`; `cleanValue` odrzuca pola niepasujące do typu.
- **Motyw przez zmienne CSS** (`--slide-accent`, `--slide-bg`, `--slide-text`, `--slide-font`) ustawiane na kontenerze slajdu. Kroje pisma to stosy systemowe/już ładowane (bez dodatkowych pobrań).
- **Domyślny motyw** z DESIGN.md (indygo `#6366F1`, tło białe, tekst `#0A0A0A`).
- **Zgodność wsteczna:** brak `type` oznacza typ `bullets` (z opcjonalnym kodem).
- **Tryb prezentera** to widok w tej samej karcie (nie nowe okno), z zegarem od wejścia w tryb.
- **Zarządzanie slajdami** (duplikuj, góra/dół, usuń) jako przyciski przy elemencie tablicy slajdów w formularzu; wymaga rozszerzenia obsługi tablic obiektów.

## Risks / Trade-offs

- Generator formularzy zyska logikę warunkową → ryzyko regresji w edytorze quizów i ściąg. Mitigacja: zmiany opt-in przez adnotacje, test UI wszystkich typów dokumentów.
- Skalowanie miniatur może rozmywać tekst → akceptowalne, to tylko podgląd.
- Plik `index.html` rośnie → trzymamy kod czytelnie, w wydzielonych sekcjach.
