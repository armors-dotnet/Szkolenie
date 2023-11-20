# Szkolenie "Zostań GitGuru"

Poniżej przedstawiono kroki do wykonania. Każdy krok zawiera rozwiązanie w postaci polecenia/poleceń w konsoli.

## Zakładanie repozytorium i tworzenie commit-ów

- [ ] Zainicjalizuj repozytorium git-a
- [ ] Sprawdź status repozytorium

<details>
  <summary>Rozwiązanie</summary>
  
```bash
git init
git status
```

</details>

---

- [ ] Dodaj plik tekstowy o nazwie `1.txt` i zawartości:
```
Nazywam się ...
Studiuję ...
```
- [ ] Sprawdź status repozytorium

<details>
  <summary>Rozwiązanie</summary>
  
```bash
echo "Nazywam się ..." > 1.txt
echo "Studiuję ..." >> 1.txt
git status
```

</details>

---

- [ ] Zaindeksuj plik `1.txt`
- [ ] Sprawdź status repozytorium

<details>
  <summary>Rozwiązanie</summary>
  
```bash
# Dodaj tylko plik 1.txt:
git add 1.txt
# Albo, dodaj wszystkie pliki z obecnego katalogu (w tym przypadku plik '1.txt'):
git add .
git status
```

</details>

---

- [ ] Stwórz commit z wiadomością: `Initial commit`
- [ ] Sprawdź status repozytorium
- [ ] Wyświetl hostorię zmian

<details>
  <summary>Rozwiązanie</summary>
  
```bash
git commit -m "Initial commit"
git status
git log
```

</details>

---

- [ ] Zmień pierwszą linię tekstu w pliku `1.txt` tak aby plik zawierał:
```
Nazywam się ... i moim hobby jest ...
Studiuję ...
```

- [ ] Sprawdź status repozytorium
- [ ] Sprawdź wprowadzone zmiany

<details>
  <summary>Rozwiązanie</summary>
  
```bash
echo "Nazywam się ... i moim hobby jest ..." > 1.txt
echo "Studiuję ..." >> 1.txt
git status
git diff
```

</details>

---

- [ ] Stwórz commit zawierający zmiany
- [ ] Sprawdź czy oba stworzone commity są widoczne w repozytorium

<details>
  <summary>Rozwiązanie</summary>
  
```bash
git add .
git commit -m "Add info about hobby"
git log
```

</details>

---

## Poruszanie się po historii

- [ ] Przejdź na poprzedni commit i sprawdź zawartość pliku

<details>
  <summary>Rozwiązanie</summary>
  
```bash
git checkout HEAD^
# Albo: git checkout <commit SHA>
cat 1.txt
git log
git status
```

</details>

---

- [ ] Wróć na commit zawierający najnowsze zmiany

<details>
  <summary>Rozwiązanie</summary>
  
```bash
git checkout main
git log
git status
```

</details>

---

- [ ] Cofnij ostatnie zmiany

<details>
  <summary>Rozwiązanie</summary>
  
```bash
git revert HEAD
git log
cat 1.txt
```

</details>

---

- [ ] Zresetuj repozytorium do momentu z przed cofnięciem zmian

<details>
  <summary>Rozwiązanie</summary>
  
```bash
git reset HEAD^
git status
git diff
git log
```

</details>

---

- [ ] Cofnij zmiany w plikach

<details>
  <summary>Rozwiązanie</summary>
  
```bash
git reset --hard HEAD
git status
git diff
git log
```

</details>

---

## Gałęzie

- [ ] Stwórz nową gałąź o nazwie `update`

<details>
  <summary>Rozwiązanie</summary>
  
```bash
git checkout -b update
git status
```

</details>

---

- [ ] Dodaj nowy plik/pliki z dowolną zawartością i zrób commit

<details>
  <summary>Rozwiązanie</summary>
  
```bash
touch 2.txt
git add .
git commit "Add new files"
```

</details>

---

- [ ] Połącz gałąź `update` z główną gałęzią `main`

<details>
  <summary>Rozwiązanie</summary>
  
```bash
# Zmiana gałęzi na main:
git checkout main
# Dołączenie gałęzi update:
git merge update

git status
git log
```

</details>

---

## Klonowanie istniejącego repozytorium i radzenie sobie z konfliktami

- [ ] Sklonuj repozytorium z przykładami

<details>
  <summary>Rozwiązanie</summary>
  
```bash
# W innym katalogu niż początkowe repozytorium:
git clone https://github.com/armors-dotnet/Szkolenie.git dotNetSzkolenieGit
cd dotNetSzkolenieGit
```

</details>

---

- [ ] Sprawdź istniejące repozytorium (commity i gałęzie)

<details>
  <summary>Rozwiązanie</summary>
  
```bash
git log
git branch
```

</details>

---

- [ ] Połącz zawartość gałęzi `add_hello_py` do gałęzi `main`

<details>
  <summary>Rozwiązanie</summary>
  
```bash
git merge add_hello_py
```

</details>

---

- [ ] Połącz zawartość gałęzi `say_hello_backwards` do gałęzi `main`

<details>
  <summary>Rozwiązanie</summary>
  
```bash
git merge say_hello_backwards
# poprawa konfliktów
git merge --continue
```

</details>

---
