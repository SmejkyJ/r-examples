
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
*vektor je vždy jednorozměrný, velice užitečný pro ukládání jednoduchých řetězců*
```r
# příklad deklarace

# příkazem c()

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
my_vektor[4] <- 18   # zapíše na 4. pozici ve vektoru 18
print(my_vector[4])  # vypíše 18 (protože 18 je na 4. pozici ve vektoru)
```
### matrix
*matice je vždy dvourozměrná, velice užitečná pro počítání matematických rovnic a analýzy*

*Vždy obsahuje prvky stejného datového typu viz. [Základní datové typy](#Základní-datové-typy)*
```r
# příklad deklarace

# příkazem matrix(vector, nrow = cislo_radku, ncol = cislo_sloupcu, byrow = bool)
# byrow je způsob ládování zadaného vektoru do této matice

my_matrix1 <- matrix(c(1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12), nrow = 4, ncol = 3, byrow = FALSE)
my_matrix2 <- matrix(c(1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12), nrow = 4, ncol = 3, byrow = TRUE)
```
```r
# Udělá tyto matice:
# my_matrix1:
1   5   9
2   6   10
3   7   11
4   8   12

# my_matrix2:
1   2   3
4   5   6
7   8   9
10  11  12
```
```r
# příklad vyčítání, předpokládejme předchozí deklaraci

print(my_matrix1[1,3]) # vypíše 9 (protože 9 je na 1. řádku ve 3. sloupci)
print(my_matrix1[4,2]) # vypíše 8 (protože 8 je na 4. řádku ve 2. sloupci)
```
```r
# příklad editace, předpokládejme předchozí deklaraci

print(my_matrix1[2,1]) # vypíše 2 (protože 2 je na 2. řádku v 1. sloupci)
my_matrix1[2,1] <- 36  # zapíše na 2. řádek a 1. sloupec číslo 36
print(my_matrix1[2,1]) # vypíše 36 (protože 36 je na 2. řádku v 1. sloupci)
```
### array
*pole je n-rozměrné, velice užitečné pro aplikace, kde je potřeba víc než dvě dimenze. (třeba 5 dimenzí)*

*Vždy obsahuje prvky stejného datového typu viz. [Základní datové typy](#Základní-datové-typy)*

*například pro počítání krychle je matice málo rozměrná, proto můžeme použít pole*

*Možná to podle popisu nezní jako věc co by se ti mohla hodit, ale je to užitečné*

*Zatím se mi to ale nechce popisovat, takže kdyžtak dopíšu později, když bude potřeba. Ono to je totiž už docela složité*

### list
*list se ti bude zaručeně hodit, umožňuje identifikovat prvky v něm pomocí slov a né pouze podle souřadnic, jako to bylo u předchozích pokročilejších datových typů*

*Může obsahovat více datových typů najednou*

*Lze kombinovat s dalšími pokrožilejšími datovými typy*

```r
# příklad deklarace

# příkazem list()

my_list <- list(firstName = "Josef", lastName = "Krátký", age=53, height=172)
```
```r
# příklad vyčítání, předpokládejme předchozí deklaraci
print(my_list$firstName)  # vypíše Josef
print(my_list$age)        # vypíše 53
# další způsob vyčítání
print(my_list[["firstName"]]) # vypíše Josef
print(my_list[["age]])        # vypíše 53
# u tohoto způsobu vyřítání však můžeme využít i vyčítání pomocí pozice (přistupuj k tomu jako kdyby to byl vektor, způsob je stejný, akorát se to jinak zapisuje)
print(my_list[[1]])  # vypíše Josef  (protože Josef je napsané v listu na 1. pozici)
print(my_list[[3]])  # vypíše 53     (protože 53 je napsané v listu na 3. pozici)
```
```r
# příklad editace, předpokládejme předchozí deklaraci

print(my_vector[4])  # vypíše 12 (protože 12 je na 4. pozici ve vektoru)
my_vektor[4] <- 18   # zapíše na 4. pozici ve vektoru 18
print(my_vector[4])  # vypíše 18 (protože 18 je na 4. pozici ve vektoru)
```

