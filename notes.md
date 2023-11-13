
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
*Toto je u programovacího jazyku R ošetřeno samopřetypovávání proměnných, tedy to vlastně vědět ani nepotřebuješ, protože to R udělá celé za tebe. Furt to je teorie, takže je dobré mít alespoň ponětí co se děje.*

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
*Přetypování (to je to co si R dělá samo)*

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
### vector
*je vždy jednorozměrný, velice užitečný pro ukládání jednoduchých řetězců*
```r
# příklad deklarace

my_vector <- c(5, 3, 8, 12, 7)
```
```r
# příklad vyčítání, předpokládejme předchozí deklaraci

print(my_vector[1])  # vypíše 5 (protože 5 je na 1. pozici ve vektoru)
print(my_vector[3])  # vypíše 8 (protože 8 je na 3. pozici ve vektoru)
```
```r
# příklad editace, předpokládejme předchozí deklaraci

print(my_vector[4])  # vypíše 12 (protože 12 je na 4. pozici ve vektoru)
my_vektor[4] = 18    # zapíše na 4. pozici ve vektoru 18
print(my_vector[4])  # vypíše 18 (protože 18 je na 4. pozici ve vektoru)
```
- matrix
- array
- list
