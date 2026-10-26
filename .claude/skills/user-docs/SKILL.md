---
name: user-docs
description: How to write and update the user manual (instrukcja dla użytkownika) of the cheatsheet app in cheatsheet/docs/. Use after every change that a user can see or use (new feature, changed behaviour, removed option, new screen), when the user asks to write, update or fix the documentation or manual, or when adding a new article to the docs sidebar.
---

# Dokumentacja użytkownika

Instrukcja opisuje **co robi aplikacja i jak z niej korzystać**. Nie opisuje kodu, struktury plików ani szczegółów technicznych. Czytelnik to osoba używająca aplikacji (uczestnik szkolenia, autor ściągi albo prezentacji), a nie programista.

## Gdzie leży dokumentacja

- Artykuły: `cheatsheet/docs/*.md`, płaskie, bez podkatalogów.
- Strona: `#/help/<nazwa-pliku-bez-.md>`, np. `#/help/edytor`. Lewy sidebar wypisuje wszystkie artykuły posortowane po `order`.
- Startowy artykuł to `index.md` (tytuł „Pierwsze kroki”, `order: 1`).

## Format pliku

Każdy plik zaczyna się nagłówkiem YAML z dwoma polami:

```markdown
---
title: Edytor dokumentów
order: 4
---

Treść artykułu…
```

- `title` – nazwa w sidebarze i w nagłówku strony. Krótka, po polsku.
- `order` – liczba decydująca o kolejności w sidebarze. Nowy artykuł daj w odpowiednim miejscu, a w razie potrzeby przenumeruj pozostałe.
- Nazwa pliku: małe litery, cyfry i myślniki, np. `prezentacje.md`. Bez polskich znaków i spacji.

## Obsługiwana składnia Markdown

Używaj tylko tych elementów:

- nagłówki `##` i `###` (poziom `#` zostaw na tytuł strony, który i tak pochodzi z `title`),
- akapity, **pogrubienie**, *kursywa*, `kod w linii`,
- listy punktowane i numerowane,
- bloki kodu z ` ``` ` (np. komendy do skopiowania),
- tabele i cytaty (`>`),
- linki do innych artykułów w formie `[Edytor](edytor.md)`. Linki zewnętrzne `https://…` też działają.

Nie używaj obrazków ani HTML-a w treści. Aplikacja ich nie przewiduje.

## Styl pisania

- Piszemy po polsku, do zwykłego użytkownika. Zdania krótkie, w trybie oznajmującym lub bezosobowym („Kliknij przycisk…”).
- Opisuj zadania krok po kroku: „Aby zobaczyć slajdy, otwórz prezentację, a potem użyj strzałek `←` i `→`.”
- Nazwy przycisków i elementów pisz tak, jak wyglądają w aplikacji, w cudzysłowie polskim: przycisk „Pobierz JSON”.
- Każdy artykuł zaczyna się od jednego zdania o tym, do czego służy funkcja.
- Nie wklejaj fragmentów kodu źródłowego ani nazw funkcji. Wyjątkiem są komendy, które użytkownik ma wpisać, i przykłady JSON, które ma przygotować.
- Nie opisuj wewnętrznych zasad (np. „dane są zapisywane w `localStorage`”), chyba że wpływają na to, co użytkownik zobaczy. Wtedy napisz to prostym językiem: „Własne dokumenty są widoczne tylko w tej przeglądarce”.

## Kiedy i jak aktualizować

Po każdej zmianie, która jest widoczna dla użytkownika, wykonaj te kroki w tym samym commicie co zmiana:

1. **Znajdź dotknięte artykuły.** Przeszukaj `cheatsheet/docs/` pod kątem nazwy funkcji, przycisku albo ekranu, którego dotyczy zmiana.
2. **Zaktualizuj treść.** Zmień opis tak, żeby pasował do nowego zachowania. Usuń opis funkcji, która zniknęła.
3. **Dodaj nowy artykuł**, jeśli zmiana to nowa, samodzielna funkcja, którą trzeba wytłumaczyć. Ustaw `title` i `order`.
4. **Sprawdź linki.** Każdy link `(nazwa.md)` musi wskazywać na istniejący plik w `docs/`.
5. **Sprawdź stronę.** Uruchom aplikację i otwórz `#/help/<slug>` zmienionego artykułu. Sprawdź, czy treść się renderuje, a sidebar pokazuje właściwe pozycje.

Zmiany niewidoczne dla użytkownika (refaktoryzacja, poprawki wewnętrzne, zmiany w README dla programistów) nie wymagają aktualizacji instrukcji.

## Czego nie robić

- Nie pisz dokumentacji technicznej (architektura, schematy, opis kodu). Ona nie należy do `docs/`.
- Nie zostawiaj opisów funkcji, których już nie ma.
- Nie duplikuj tej samej instrukcji w kilku artykułach. Jeden temat, jeden artykuł, z linkiem z innych.

Na końcu każdego artykułu napisz pozdrowienia dla użytkownika
