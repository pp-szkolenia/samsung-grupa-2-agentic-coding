# presentation-pdf-export Specification

## Purpose
Eksport prezentacji do pliku PDF, który użytkownik może zapisać na dysku i pobrać, bez dodatkowych narzędzi poza przeglądarką.

## ADDED Requirements

### Requirement: Export button
Viewer prezentacji SHALL pokazywać przycisk „Eksportuj do PDF”, który uruchamia eksport całej prezentacji.

#### Scenario: Uruchomienie eksportu
- **WHEN** użytkownik klika „Eksportuj do PDF” w widoku prezentacji
- **THEN** otwiera się okno drukowania przeglądarki z podglądem wszystkich slajdów

### Requirement: One slide per page
Eksport SHALL umieszczać każdy slajd na osobnej stronie w proporcjach 16:9, w kolejności prezentacji, bez marginesów i bez elementów interfejsu (nawigacja, miniatury, notatki, pasek postępu).

#### Scenario: Prezentacja z 6 slajdami
- **WHEN** użytkownik eksportuje prezentację z 6 slajdami, będąc na slajdzie 3
- **THEN** PDF ma 6 stron, każda zawiera jeden slajd od pierwszego do ostatniego

### Requirement: Theme fidelity
Eksport SHALL zachowywać kolory tła i tekstu, kolor akcentu oraz krój pisma z motywu prezentacji.

#### Scenario: Ciemny motyw
- **WHEN** prezentacja ma ciemne tło i jasny tekst
- **THEN** strony PDF mają to samo tło i kolory, a nie białe tło

### Requirement: Default file name
Eksport SHALL proponować nazwę pliku opartą na tytule prezentacji, a po zamknięciu okna drukowania viewer SHALL wrócić do poprzedniego widoku bez zmiany stanu (aktualny slajd, tryb prezentera).

#### Scenario: Nazwa pliku
- **WHEN** prezentacja ma tytuł „Vibe coding”
- **THEN** okno zapisu PDF proponuje nazwę zaczynającą się od „Vibe coding”

#### Scenario: Powrót po eksporcie
- **WHEN** użytkownik zamknie okno drukowania
- **THEN** viewer pokazuje ten sam slajd co przed eksportem, a tytuł karty przeglądarki jest przywrócony
