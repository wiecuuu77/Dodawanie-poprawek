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
diff -u lista.txt lista-pop.txt > aktualizacja.patch