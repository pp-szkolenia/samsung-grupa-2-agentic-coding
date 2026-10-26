## ADDED Requirements

### Requirement: Presentation theme
Prezentacja SHALL mieć opcjonalne pole `theme` z kolorem akcentu, kolorem tła, kolorem tekstu i krojem pisma z ustalonej listy (sans-serif, serif, monospace, display).

#### Scenario: Zmiana motywu
- **WHEN** użytkownik zmienia kolor akcentu lub krój pisma w edytorze
- **THEN** podgląd na żywo oraz viewer używają nowego stylu na wszystkich slajdach

#### Scenario: Brak motywu
- **WHEN** prezentacja nie ma pola `theme`
- **THEN** używany jest motyw domyślny zgodny z DESIGN.md

### Requirement: Readable colors
Edytor SHALL ostrzegać, gdy kontrast między kolorem tła i tekstu jest zbyt niski.

#### Scenario: Niski kontrast
- **WHEN** użytkownik wybierze tło i tekst o podobnej jasności
- **THEN** edytor pokazuje ostrzeżenie o słabej czytelności, nie blokując zapisu
