---
name: git-usage
description: How to use Git in this repository. Use whenever you finish a meaningful change and need to commit it, write a commit message, push, create a branch, or check repository state, or when the user mentions commit, push, branch, or git.
---

# Git usage

## Zasady

1. **Commit po każdej większej zmianie.** Jedna logicznie spójna część pracy = jeden commit. Nie mieszaj niezwiązanych zmian.
2. **Po każdym commicie zawsze rób push** w tym samym kroku, bez osobnego pytania, żeby `origin` był zawsze aktualny. Commit bez push jest niekompletny.
3. **Dodawaj konkretne pliki** (`git add <pliki>`), nie `git add .`. Przed commitem sprawdź `git status` i `git diff`.
4. **Nie commituj sekretów** (hasła, tokeny, pliki `.env`).
5. **Nie niszcz historii bez pytania**: bez `push --force`, `reset --hard` i rebase na udostępnionych gałęziach.
6. **Nie zmieniaj `user.name` ani `user.email`.** Autorem jest użytkownik repozytorium.

## Komunikaty commitów

Conventional Commits: `typ(zakres): krótki opis`, po angielsku, w trybie rozkazującym, bez kropki na końcu, do ok. 72 znaków.

- Typy: `feat`, `fix`, `docs`, `style`, `refactor`, `chore`, `test`.
- Zakres opcjonalny, np. `cheatsheet`, `docker`, `design`, `skills`.
- Na końcu komunikatu dodaj trailer:

```
Co-Authored-By: Claude Haiku 5.5 <noreply@anthropic.com>
```

Przykład:

```
feat(cheatsheet): add keyboard shortcuts section

Co-Authored-By: Claude Haiku 5.5 <noreply@anthropic.com>
```

## Przepływ

1. `git status` i `git diff`
2. `git add <pliki>`
3. `git commit` z komunikatem wg konwencji
4. `git push` – zawsze, po każdym commicie (nowa gałąź: `git push -u origin <gałąź>`)

Gdy push zostanie odrzucony, nie wymuszaj go. Zsynchronizuj się (`git pull --rebase`) i zapytaj użytkownika, jeśli pojawią się konflikty.
