# Raport z wykonania zadania - Łatka (Patch)
## Użyte komendy w terminalu:
```bash
  352  cleatr
  353  em aktualizacja.patch 
  354  rm aktualizacja.patch 
  355  rm lista.txt.orig 
  356  diff - u lista.txt lista-pop.txt 
  357  diff - u lista.txt lista-pop.txt > aktualizacja.patch
  358  patch lista.txt < aktualizacja.patch 
  359  md5sum.exe lista.txt lista-pop.txt 
  360  diff -u lista.txt lista-pop.txt > aktualizacja.patch
  361  patch lista.txt < aktualizacja.patch
  362  md5sum lista.txt lista-pop.txt
  363  echo "# Raport z wykonania zadania - Łatka (Patch)" > wykonane_kroki.md
  364  echo "## Użyte komendy w terminalu:" >> wykonane_kroki.md
  365  echo "\`\`\`bash" >> wykonane_kroki.md
  366  history | tail -n 15 >> wykonane_kroki.md
```
## Weryfikacja sum kontrolnych MD5:
```text
683c1c85343c7337adfb13acb7598237 *lista.txt
683c1c85343c7337adfb13acb7598237 *lista-pop.txt
```
