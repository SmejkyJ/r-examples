
# R - Doučko

## Deklarace proměnných
```r
# příklad deklarace

my_value = 5
my_value <- 5
5 -> my_value
```
*Zde zavádíme novou proměnnou my_value s inicializeční hodnotou 5. Všechny 3 řádky dělají stejnou věc, jde pouze o způsob zápisu.*

*Proměnná může v programovacím jazyku R může kdykoli měnit svůj datový typ viz. [Základní datové typy](#Základní-datové-typy)*
___
## Základní datové typy
*Toto je u programovacího jazyku R ošetřeno samopřetypovávání proměnných, tedy to vlastně vědět ani nepotřebuješ, protože to R udělá celé za tebe.*

*Máme jich hned několik:*
- string - je textový řetězec
- int - je celé číslo
- float - je desetinné číslo
- bool - je dvoustavová proměnná (tedy buď TRUE nebo FALSE)
```r
# příklad datových typů

my_value <- "Ahoj"    # string
my_value <- 189       # int
my_value <- 3.1459    # float
my_value <- FALSE     # bool
```
*Přetypování*

*Lze změnit datový typ, přiřazením hodnoty, která neodpovídá aktuálnímu datovému typu*
```r
# příklad přetypování

my_value <- 5
my_value <- "jablko"
```

*proměnná my_value byla inicializována jako int s hodnotou 5, ale později se do my_value snažíme zapsat string jablko, což není int. my_value se tedy přetypuje na string a až poté se zapíše hodnota jablko*
___
## Pokročilé datové typy
*Toto je potřeba alespoň trochu pochytit, velice důležité na komplexnější problémy*
- vector - vektor je vždy jednorozměrný, velice užitečný pro ukládání jednoduchých řetězců
```r
# příklad deklarace přepsání a čtění vektoru

my_vector = 
```
- matrix
- array
- list
