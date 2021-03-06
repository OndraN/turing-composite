Turing Composite
================
Deterministic turing machine simulator in composite format


Umoznuje simulaci TS v kompozitnim modelu. Obsahuje:
 - model TS
 - prechod R
 - prechod L
 - prechod L_x
 - prechod R_x
 - nahradu symbolu C - mozno zadat primo (misto C("a") jenom "a")
 - ukladani do pameti
 - cteni z pameti
 - Shift left (Sl)
 - Shift right (Sr)

Blank symboly jsou definovany pomoci symbolu podtrzitka "_"


Vice informaci a ukazka moznosti v prikladech.

Nekonecna paska neni implementovana, na zacatek je nutne vlozit na pasku okolo dostatecne mnozstvi blank symbolu


Vystup je barevny pro unixove konzole, kdy se cervenou barvou ukazuje pozice cteci hlavy

Negace symbolu
==========================
U prechodu a u posunu vlevo / vpravo jsme schopni definovat prechod s opacnou logikou (negaci). Ta se definuje tak, ze zadame prechod pro "!x"

Tichy rezim
=========================
Nastavenim promenne verbose (nebo konstrukce TS s parametrem false) skryje veskere debug data.
Vysledna data z pasky jsou v promene tape TS.

Pristup k pameti
=========================
Pro cteni symbolu z pameti neni nutne pouzivat prvek C s prvkem MemRead, ale staci pouzit samotny MemRead s prvkem v konstruktoru ts a jmeno promenne

Prechod pres vice promennych
=============================
Pokud prechod definujeme pro seznam (napr ["x", "y", "z"]), tak se definuje pro kazdy ze symbolu.

Generovani obrazku
==========================
Kdyz nagenerujeme TS, tak misto funkce "test" importujeme kreslici knihovnu
  
```python
from ts import *
ts=TuringMachine()
# inicializace TS

print ToGraph(ts)
```

Tento stroj transformujeme na obrazek pres
```
python test.py | dot -Tpng -o output.png
```

Pripadne muzeme transformovat data do jineho formatu (napr svg) a ten pak upravit

