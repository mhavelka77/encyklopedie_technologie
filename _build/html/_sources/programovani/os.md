# Operační systém

V kapitole o fungování procesoru byl popsán princip vykonávání jednotlivých instrukcí z paměti počítače. Jsme schopni napsat počítačový program např. v jazyce C a následně ho kompilovat do binární formy, tj. instrukcí, které následně nějakým způsobem nahrajeme do RAM a konečně spustíme. 

Tento model je ale ještě poměrně daleko od popsání funkčnosti dnešních PC: 

- Jak je možné, že na PC může běžet několik programů najednou?
- I když chápu koncept jednoduchých instrukcí jako MOV a ADD, jak je možné z nich postavit něco tak komplexního jako jsou hry/youtube/excel?

`````{admonition} TL;DR 
:class: danger 
Operační systém je dlouhý a komplexní program, který je spuštěn jako první[^1] při zapnutí počítače. Umožňuje celou plejádu funkcí včetně paralelního běhu ostatních programů.
`````

V následujících podsekcích je popsáno několik obecných mechanismů používaných operačními systémy, které považuji za důležité.

[^1]: Tohle tvrzení není tak úplně pravda, ale zatím to postačí.