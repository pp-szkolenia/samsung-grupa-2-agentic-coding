## 1. Eksport w viewerze

- [x] 1.1 Dodać przycisk „Eksportuj do PDF” do paska sterowania w `buildDeck` (nieaktywny bez slajdów) i sprawdzić, że widać go także w trybie prezentera oraz że działa z klawiatury (Tab + Enter)
- [x] 1.2 Zaimplementować funkcję eksportu: budowa `#print-deck` ze wszystkimi slajdami, ustawienie `document.title` na tytuł prezentacji, `window.print()`, sprzątanie w `afterprint`; zweryfikować w przeglądarce, że po zamknięciu okna drukowania aktualny slajd, tryb prezentera i tytuł karty są bez zmian

## 2. Style druku

- [x] 2.1 Dodać `@page` (16:9, bez marginesów) i `@media print`: ukrycie reszty strony, jeden slajd na stronę, zachowanie kolorów tła; zweryfikować `page.pdf` w Playwright: liczba stron = liczba slajdów
- [x] 2.2 Sprawdzić wizualnie PDF dla prezentacji z `examples/presentations` (jasny i ciemny motyw, wszystkie 6 typów slajdów) i poprawić przycięcia lub przepełnienia

## 3. Dokumentacja i zgodność

- [x] 3.1 Dodać sekcję „Eksport do PDF” w `cheatsheet/docs/prezentacje.md` (skill `user-docs`), z wskazówką o opcji „Grafika w tle” i o wyborze „Zapisz jako PDF”; sprawdzić widok `#/help`
- [x] 3.2 Zaktualizować `cheatsheet/README.md` i sprawdzić zgodność wyglądu przycisku z `DESIGN.md`
- [x] 3.3 Uruchomić agenta `ui-tester` na całym przepływie (otwarcie prezentacji, eksport, brak regresji nawigacji) i zrobić commit
