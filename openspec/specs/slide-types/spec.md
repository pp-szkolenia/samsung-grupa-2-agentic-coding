# slide-types Specification

## Purpose
TBD - created by archiving change rich-presentation-editor. Update Purpose after archive.

## Requirements

### Requirement: Slide types
Slajd SHALL mieć pole `type` o jednej z wartości: `title`, `text`, `bullets`, `two-columns`, `quote`, `code`. Każdy typ SHALL mieć własny układ w viewerze i własny zestaw pól w edytorze.

#### Scenario: Wybór typu w edytorze
- **WHEN** użytkownik zmienia typ slajdu w edytorze
- **THEN** formularz pokazuje pola dla tego typu (np. `quote` ma tekst cytatu i autora, `two-columns` ma lewą i prawą kolumnę)

#### Scenario: Render typu w viewerze
- **WHEN** viewer wyświetla slajd typu `quote`
- **THEN** cytat jest pokazany w dużym, wyśrodkowanym układzie z autorem pod spodem

### Requirement: Backward compatibility
Slajd bez pola `type` SHALL być wyświetlany jak dotychczas: jako tytuł z opcjonalnymi punktami i kodem.

#### Scenario: Stara prezentacja
- **WHEN** użytkownik otwiera prezentację zapisaną w starym formacie
- **THEN** wszystkie slajdy są poprawnie wyświetlane i przechodzą walidację

### Requirement: Slide management
Edytor SHALL umożliwiać dodawanie, usuwanie, duplikowanie i zmianę kolejności slajdów.

#### Scenario: Zmiana kolejności
- **WHEN** użytkownik przesuwa slajd w górę lub w dół
- **THEN** kolejność w JSON i w podglądzie jest zaktualizowana
