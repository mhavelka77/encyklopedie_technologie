# Hradla

Zapojením několika transistorů do většího logického obvodu získáme takzvané **hradlo** (nebo logický člen, anglicky logic gate).  

Hradla mají svoje vstupy a výstupy a proto pro ně můžeme také vytvořit pravdivostní tabulky. Následuje výčet důležitých hradel, které budeme potřebovat. U každého hradla se podívejte na jeho schéma uvědomte si, že jeho pravdivostní tabulka odpovídá zapojení. 

`````{admonition} Poznámka 
:class: note 
Tohle je ideální příklad "zapouzdřování složitosti". Místo toho, abychom se zabývali jednotlivými transistory v hradlech (natož proudy a napětí), jednou si je tady ukážeme a pak už o hradle budeme mluvit jen jako o obdelníčku, který z nějakých vstupů vytvoří výstupy. 
`````

`````{admonition} Poznámka 2 
:class: note 
U každého hradla se pokusím popsat proč zapojení funguje, pokud máte na elektroniku alergii, igorujte. A akceptuje že hradlo funguje jako fakt.
`````

## NOT hradlo

```{figure} ./res/not.png 
:alt: NOT hradlo 
:width: 150px
:align: left 

Schématická značka NOT gate.
```

```{figure} ./res/not_schema.jpeg
:alt: NOT hradlo schema
:width: 350px
:align: right  

Elektronické schéma NOT gate.
```

```{list-table} Pravdivostní tabulka NOT gate 
:header-rows: 1
:name: pravd_not
:width: 300px
:align: left

* - Vstup 
  - Výstup 
* - 0
  - 1
* - 1
  - 0
```

Na schématu (Fig. 2) vidíme, že k sestrojení NOT gate potřebujeme jen jeden transistor (Q1). Tři čáry vedoucí ze značky transistoru korespondují se třemi nožičkami popsanými v minulé kapitole. Proud, který teče z horního výstupu do spodního je regulován napětím na levém vstupu. 

Na obrázku který jsem ukradl na internetu je vstup popsný jako A a výstup popsaný jako Ā (Což je poměrně častá symbolizace něčeho invertovaného). Zároveň je horní nožička transistoru přes resistor spojená s Vcc, což je plus, řekněme 5V a spodní nožička je spojená se zemí (tj. referenční bod obvodu, který se považuje za 0V). 

**Co se stane když na vstup, tj A dáme logickou hodnotu 1, tj. 5V?**

Transistor se "aktivuje", tj. prakticky se v něm spojí horní a dolní nožička. To znamená, že z Vcc poteče do země takový proud který dovolí resistor. Jak to ovlívní výstup Ā? Ten se prakticky přímo spojí se zemí a tudíž na něm bude napětí 0V - logická 0.

**Co se stane když na vstup A dáme logickou hodnotu 0, tj. 0V?**

Transistor při 0V na kontrolní nožičce prakticky rozpojí horní a dolní nožičku. Výstup Ā se tak přes resistor spojí s Vcc - 5V. To sice byl i v prvním případě, ale nyní je rozdíl v tom, že z Vcc neteče proud do země. Kdybych se měl pokusit o intuitivní vysvětlení bez znalostí elektroniky, asi by vypadalo takhle:

Vcc není spojena se zemí a tak mají elektrony dostatek času se přes resistor přesunout a rozprostřít i do výstupu Ā, kde svojí prezencí vytvoří napětí 5V - logickou 1. Když je naopak transistor aktivovaný a proud elektrony z Vcc tečou do země (=proud), raději se okamžitě přesunou do země než na výstup Ā, protože zem je místo, kam jsou přitahovány elektrickou silou.





## AND hradlo


```{figure} ./res/and.png 
:alt: AND hradlo 
:width: 150px
:align: left 

Schématická značka AND gate.
```

```{figure} ./res/and_schema.png
:alt: AND hradlo schema
:width: 350px
:align: right  

Elektronické schéma AND gate.
```

```{list-table} Pravdivostní tabulka AND gate 
:header-rows: 1
:name: pravd_not
:width: 300px
:align: left

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

AND hradlo má dva vstupy a vyplivne logickou 1 pouze pokud jsou oba vstupy také 1. Jeho sestrojení je banální, jen zapojíme dva transistory za sebe a díváme se, jestli teče proud. Tohle dívání provedeme stejným způsobem jako u NOT hradla, jen rezistor zapojíme až před zem.









Zdroje obrázků:
https://boxbase.org/entries/2016/may/2/robot-electronics/not-gate.jpg
https://www.waitingforfriday.com/wp-content/uploads/2017/01/Slide13.png