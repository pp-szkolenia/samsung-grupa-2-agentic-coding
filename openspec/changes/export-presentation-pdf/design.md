## Context

Slajdy są renderowane funkcją `renderSlideContent` jako elementy 16:9, skalowane jednostkami `cqw` (container queries), więc wyglądają tak samo w każdej szerokości. Viewer (`buildDeck`) pokazuje jeden slajd naraz plus miniatury. Projekt to jeden plik `index.html` bez bibliotek i bez kroku budowania. Wybrana metoda (potwierdzona przez użytkownika): druk przeglądarki.

## Goals / Non-Goals

**Goals:**
- Wierny PDF z wszystkimi slajdami, tekst zaznaczalny (wektorowy).
- Zero nowych zależności.

**Non-Goals:**
- Bezpośrednie pobranie pliku jednym kliknięciem bez okna drukowania.
- Eksport notatek prezentera, eksport quizów i ściąg.
- Zapisywanie PDF-ów po stronie serwera lub w aplikacji.

## Decisions

- **`window.print()` zamiast html2canvas + jsPDF.** Daje wektorowy PDF, nie wymaga CDN ani kroku budowania. Koszt: plik zapisuje okno drukowania („Zapisz jako PDF”), nie sama aplikacja.
- **Kontener `#print-deck` budowany na żądanie.** Przed drukiem aplikacja dokłada do `body` kontener ze wszystkimi slajdami (`renderSlideContent` dla każdego), a po zdarzeniu `afterprint` go usuwa. Dzięki temu nie dublujemy DOM-u na stałe i stan viewera (`state.slide`, tryb prezentera) pozostaje nietknięty.
- **CSS `@media print`.** Ukrywa całą resztę strony (`body > *:not(#print-deck)`), `@page { size: 297mm 167mm; margin: 0 }`, każdy slajd w `page-break-after: always` z `break-inside: avoid`, `print-color-adjust: exact` dla teł. Slajd w druku ma stałą szerokość 297mm, żeby `cqw` skalowało się poprawnie.
- **Nazwa pliku:** na czas druku `document.title` = tytuł prezentacji, przywracany w `afterprint`. Przeglądarki używają tytułu jako domyślnej nazwy.
- **Jawny motyw w druku:** ciemny/jasny motyw aplikacji nie wpływa na slajdy, bo mają własne kolory z `theme`; reguły druku nie mogą polegać na zmiennych motywu aplikacji.

## Risks / Trade-offs

- [Użytkownik zostawi w oknie druku nagłówki i stopki przeglądarki] → `@page { margin: 0 }` je zwykle ukrywa; opisać w dokumentacji opcję „Grafika w tle” w Chrome (kolory teł) jako wskazówkę.
- [Przeglądarka domyślnie nie drukuje teł] → `print-color-adjust: exact` / `-webkit-print-color-adjust: exact`; weryfikacja w Chromium i Firefox.
- [Różnice między przeglądarkami w `@page size`] → sprawdzić w Chromium (Playwright `page.pdf`) i ręcznie w Firefoksie.
- [Duże prezentacje drukują się wolno] → akceptowalne dla skali szkoleniowej.
