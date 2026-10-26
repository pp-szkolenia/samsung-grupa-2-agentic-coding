## 1. Schemat i dane

- [x] 1.1 Rozszerzyć `presentation.schema.json`: pole `type` (enum), pola typów, `theme` (kolory, krój pisma), adnotacje `x-showFor`, `x-format`
- [x] 1.2 Zaktualizować przykładowe prezentacje w `examples/presentations/` tak, by używały różnych typów slajdów i motywów

## 2. Renderowanie slajdów

- [x] 2.1 Zaimplementować `renderSlideContent(slide, theme)` dla typów title, text, bullets, two-columns, quote, code (z zachowaniem starego formatu bez `type`)
- [x] 2.2 Dodać style CSS slajdów (kontener 16:9, zmienne motywu, domyślny motyw wg DESIGN.md)

## 3. Edytor

- [x] 3.1 Rozszerzyć generator formularzy o listę wyboru, pole koloru i pola warunkowe `x-showFor`; dostosować `cleanValue` i walidację
- [x] 3.2 Dodać edycję motywu (kolory, krój pisma) z ostrzeżeniem o niskim kontraście
- [x] 3.3 Dodać zarządzanie slajdami: dodaj, usuń, duplikuj, góra/dół
- [x] 3.4 Dodać podgląd aktualnego slajdu na żywo obok formularza

## 4. Viewer

- [x] 4.1 Dodać panel miniatur i pasek postępu
- [x] 4.2 Dodać podgląd następnego slajdu
- [x] 4.3 Dodać tryb prezentera (notatki, następny slajd, zegar)
- [x] 4.4 Dodać skróty klawiszowe (strzałki, spacja, Home/End, F, P)

## 5. Dokumentacja i weryfikacja

- [x] 5.1 Zaktualizować `docs/prezentacje.md` i `docs/edytor.md` (skill `user-docs`) oraz `cheatsheet/README.md`
- [ ] 5.2 Sprawdzić zgodność wyglądu z `DESIGN.md`
- [x] 5.3 Przetestować UI agentem `ui-tester` (viewer, edytor, stare prezentacje, quizy i ściągi bez regresji)
- [x] 5.4 Zrobić commit
