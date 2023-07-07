# Paralelismus

Paralelismus (multitasking) je schopnost počítače/operačního systému spouštět více procesů[^1] najednou. 

`````{admonition} Příklad 
:class: example 
S určitou pravděpodobností na Vašem počítači právě běží tyto procesy:

- Webový prohlížeč, pomocí kterého čtete tento text
- Proces, který umožňuje ostatním procesům (např. prohlížeči) vykreslovat grafický obsah a komunikovat s grafickou kartou (window manager)
- proces, který zachytává vstup z klávesnice a myši a propaguje ho do ostatních relevantních aplikací. [^2]
- Microsoft Word
`````

Jak této schopnosti docílit?

Po spuštění PC jsme v situaci, kdy na procesoru běží operační systém, který byl nahrán z disku PC. Pokud chce operační systém předat kontrolu jinému programu, stačí tento program pouze najít najít na disku, zkopírovat ho do paměti RAM a pak jen namířit PC registr. 

V tuto chvíli se ale ukazuje podstatný problém: **Jak donutit běžící program, aby předal kontrolu zpět operačnímu systému?**

Řešení tohoto problému spočívá v několika mechanismech, které jsou implementované jak v operačním systému, tak v procesoru samotném. Např. v procesoru existují tzv. Timery, které po uplynutí určitého času pošlou signál procesoru (tzv. interrupt), který zapříčiní okamžitý přepis PC registru na nějakou specifikovanou adresu v kódu operačního systému. 

Dalším způsobem jak operační systém přebírá kontrolu jsou tzv. systémová volání (system call, syscall). Pokud proces potřebuje přístup k nějakému zdroji, který má na starost operační systém (např. zápis do souboru), proces prostřednictvím systémového volání "požádá" operační systém aby mu tento zdroj zpřístupnil.

`````{admonition} Poznámka 
:class: note
Prakticky se v x86 syscall volá pomocí instrukce SYSCALL, která automaticky přepíše PC registr na specifikovanou adresu, na které se nachází funkce operačního systému, která se postará o zbytek. Výčet syscallů pro x64 je např. zde: 

https://filippo.io/linux-syscall-table/
`````

Co se tedy právě teď ve vašem PC děje, se dá shrnout jako extrémně rychlé střídání všech možných procesů a operačního systému samotného, který ostatním procesům podle různých kritérií přiděluje čas, který na běh na procesoru dostanou[^3]. **Skutečný paralelismus, je tedy většinou lež, počítače jsou jen velmi rychlé.**


`````{admonition} Varování 
:class: warning 
Všimněte si, že v tomto krátkém vysvětlení paralelismu není ani zmínka o vícejádrových procesorech. Je to proto, že i když jsou samozřejmě hojně používány, nejsou tím, co umožňuje paralelismus a multitasking. Pokud se o operačních systémech učíte poprvé, doporučuji se konceptu více jader vyhnout a ještě chvíli ho pro pochopení základních principů igorovat.
`````

[^1]: Proces se dá definovat jako běžící program - je nahraný v paměti počítače a procesor vykonává jeho instrukce.
[^2]: Tento software je ale typicky součástí operačního systému...
[^3]: Pro více informací hledejte např. Round robin. 