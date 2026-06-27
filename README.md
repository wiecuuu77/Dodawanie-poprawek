# Sprawozdanie: Aktualizacja bazy danych słów za pomocą łatki (Patch) i weryfikacja MD5


## 1. Cel zadania
Głównym celem zadania było porównanie dwóch wersji plików tekstowych (`lista.txt` oraz `lista-pop.txt`), zidentyfikowanie wprowadzonych zmian, a następnie wygenerowanie i nałożenie łatki aktualizacyjnej (patch). Ostatnim etapem była weryfikacja spójności danych przy użyciu algorytmu funkcji skrótu MD5 oraz przesłanie zmian do repozytorium Git.

## 2. Wykorzystane narzędzia
* **Środowisko:** Visual Studio Code (VS Code)
* **Terminal:** Bash (integracja z MSYS2 / Git Bash)
* **Narzędzia konsolowe:** `diff`, `patch`, `md5sum`, `git`

## 3. Przebieg prac i wykonane polecenia

### Krok 1: Analiza różnic i wygenerowanie łatki
Za pomocą polecenia `diff` porównano oryginalny plik z wersją poprawioną i wygenerowano plik różnicowy w formacie zunifikowanym (`-u`).

```bash
diff -u lista.txt lista-pop.txt > aktualizacja.patch.
```

### Krok 2: Rozwiązanie problemu ze znakami końca linii (CRLF vs LF)
Podczas próby nałożenia łatki wystąpił błąd different line endings (Hunk FAILED). Wynikał on z różnic w kodowaniu znaków końca linii pomiędzy systemem Windows (CRLF) a standardem uniksowym (LF), którego wymagało narzędzie patch.
Rozwiązanie:
Z poziomu edytora VS Code ujednolicono formatowanie w obu plikach, zmieniając CRLF na LF. Następnie plik aktualizacja.patch wygenerowano ponownie, co wyeliminowało błędy kompatybilności. Alternatywnie, z poziomu terminala odrzucono nieudane zmiany
```bash
rm lista.txt.rej
```

### Krok 3: Nałożenie łatki aktualizacyjnej
Po rozwiązaniu problemu z formatowaniem, łatka została pomyślnie nałożona na oryginalny plik tekstowy za pomocą operatora przekierowania.
patch lista.txt < aktualizacja.patch

### Krok 4 Weryfikacja sum kontrolnych
Aby potwierdzić, że zaktualizowany plik lista.txt jest w 100% identyczny z plikiem referencyjnym lista-pop.txt, obliczono i porównano ich sumy kontrolne MD5.
md5sum lista.txt lista-pop.txt