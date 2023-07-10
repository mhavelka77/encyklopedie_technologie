# Transistor

Transistor je elektronická součástka s třemi nožičkami, jejíž funkce je velmi jednoduchá: Napětí/proud který bude přítomen na první nožičce je přímo ovlivňuje proud který poteče mezi druhou a třetí nožičkou. Vypadá třeba takhle:

```{image} ./res/transistor.png 
:alt: Transistor
:width: 250px
:align: center
```


V tuto chvíli je potřeba jasně vymezit rozsah tohoto textu. V definici transistoru se objevuje proud a napětí a to už vyžaduje minimálně znalost středoškolské fyziky. Před pokračováním tedy zavedeme podstatné zjednodušení které budeme používat. 

Místo popisování napětí a proudů se budeme bavit o tzv. logických hodnotách. Jedoduše řekneme že něco má logickou hodnotu 1 nebo 0. (Reálně to např. bude znamenat že napětí mezi zkoumaným bodem a zemí je více než/méně než nějaká stanovená hodnota)

`````{admonition} Příklad 
:class: example 
Pokud se budeme na jednoduchý vodič dívat jako na součástku se vstupem a výstupem, můžeme o ní říct, že logická hodnota na výstupu je rovna logické hodnotě na vstupu. 
`````

**Nová definice transistoru:**

Transistor je součástka, která má dva vstupy a jeden výstup. Pokud na prvním vstupu bude logická hodnota 1, na výstupu bude ta samá logická hodnota jako na druhém vstupu. Pokud na prvním vstupu bude 0, na výstupu bude také 0.

Tenhle popis sice stačí, ale možná jste si text museli přečíst dvakrát abyste si ujasnili jak se výstup bude měnit v závislosti na vstupech. Existuje daleko lepší reprezentace - vstupy i výstupy mohou nabývat jen dvou hodnot: 1 nebo 0. Proto se dá jednoduše sestrojit tablulka, která pokrývá všechny kombinace hodnot které mohou nastat:

```{list-table} Pravdivostní tabulka transistoru
:header-rows: 1
:name: pravd_transistor 

* - Vstup 1 
  - Vstup 2
  - Výstup 
* - 0
  - 0
  - 0
* - 0
  - 1
  - 0
* - 1
  - 0
  - 0
* - 1
  - 1
  - 1
```

Takovéhle tabulce se říká pravdivostní tabulka.


`````{admonition} Poznámka 
:class: note 
Části matematiky která se zabývá pravdivostními hodnotami a výroky se říká výroková logika. Budu se od ní snažit co nejdříve vzdálit. 
`````

V další kapitole uvidíme, že pokud chytře spojíme několik transistorů za sebe, můžeme sestrojit logické obvody, které dokází provádět šikovné funkce, jako je třeba sčítání dvou čísel.