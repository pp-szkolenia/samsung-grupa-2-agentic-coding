# presentation-viewer Specification

## Purpose
TBD - created by archiving change rich-presentation-editor. Update Purpose after archive.

## Requirements

### Requirement: Slide navigation panel
Viewer SHALL pokazywać listę miniatur slajdów oraz pasek postępu; kliknięcie miniatury SHALL przechodzić do slajdu.

#### Scenario: Skok do slajdu
- **WHEN** użytkownik klika miniaturę slajdu 5
- **THEN** viewer wyświetla slajd 5 i licznik pokazuje „5 / N"

### Requirement: Next slide preview
Viewer SHALL pokazywać podgląd następnego slajdu obok aktualnego; na ostatnim slajdzie SHALL pokazywać informację o końcu prezentacji.

#### Scenario: Podgląd następnego
- **WHEN** użytkownik jest na slajdzie 2 z 6
- **THEN** podgląd pokazuje slajd 3

### Requirement: Presenter mode
Viewer SHALL mieć tryb prezentera z aktualnym slajdem, następnym slajdem, notatkami i zegarem czasu prezentacji.

#### Scenario: Włączenie trybu prezentera
- **WHEN** użytkownik włącza tryb prezentera
- **THEN** widzi notatki bieżącego slajdu i podgląd kolejnego

### Requirement: Keyboard shortcuts
Viewer SHALL obsługiwać skróty: strzałki i spacja (nawigacja), `Home`/`End` (pierwszy/ostatni slajd), `F` (pełny ekran), `P` (tryb prezentera).

#### Scenario: Pełny ekran skrótem
- **WHEN** użytkownik naciśnie `F`
- **THEN** slajd przechodzi w tryb pełnoekranowy

### Requirement: Live preview in editor
Edytor prezentacji SHALL pokazywać podgląd aktualnie edytowanego slajdu na żywo.

#### Scenario: Edycja tytułu
- **WHEN** użytkownik wpisuje tytuł slajdu
- **THEN** podgląd aktualizuje się bez zapisywania
