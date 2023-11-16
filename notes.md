
# R - Doučko

## Operátory
### Aritmetické operátory
```r
+    #- plus
-    #- mínus
*    #- krát
/    #- děleno
%%   #- zbytek po dělení
^    #- mocnina
```
### Relační operátory
```r
==   #- rovná se 
<    #- menší než
>    #- vetší než
<=   #- menší nebo rovná se
>=   #- větší nebo rovná se
!=   #- nerovná se
```
### Logické operátory
```r
&    #- AND 
|    #- OR
```

## Deklarace proměnných
```r
# příklad deklarace

my_value = 5
my_value <- 5
5 -> my_value
```
*Zde zavádíme novou proměnnou my_value s inicializeční hodnotou 5. Všechny 3 řádky dělají stejnou věc, jde pouze o způsob zápisu.*

*Proměnná může v programovacím jazyku R může kdykoli měnit svůj datový typ viz. [základní datové typy](#Základní-datové-typy)*
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
### Přetypování (to je to co si R dělá samo)

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

*Další způsob deklarace vektoru (hodí se to u [cyklů](#Cykly))*
```r
# příklad speciální deklarace

my_vektor <- (1:5) # vytvoří vektor s čísly 1, 2, 3, 4 a 5

# ekvivalentní zápis by vypadal takto:

my_vektor <- c(1, 2, 3, 4, 5)

```
### matrix
*matice je vždy dvourozměrná, velice užitečná pro počítání matematických rovnic a analýzy*

*Vždy obsahuje prvky stejného datového typu viz. [základní datové typy](#Základní-datové-typy)*
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

*Vždy obsahuje prvky stejného datového typu viz. [základní datové typy](#Základní-datové-typy)*

*například pro počítání krychle je matice málo rozměrná, proto můžeme použít pole*

*Možná to podle popisu nezní jako věc co by se ti mohla hodit, ale je to užitečné*

*Zatím se mi to ale nechce popisovat, takže kdyžtak dopíšu později, když bude potřeba. Ono to je totiž už docela složité*

### list
*list se ti bude zaručeně hodit (asi nejdůležitěší za všech), umožňuje identifikovat prvky v něm pomocí slov a né pouze podle souřadnic, jako to bylo u předchozích pokročilejších datových typů*

*Může obsahovat více datových typů najednou viz. [základní datové typy](#Základní-datové-typy)*

*Lze kombinovat s dalšími pokrožilejšími datovými typy*

```r
# příklad deklarace

# příkazem list()

my_list <- list(firstName = "Josef", lastName = "Krátký", age = 53, height = 172)
```
```r
# příklad vyčítání, předpokládejme předchozí deklaraci

print(my_list$firstName)  # vypíše Josef
print(my_list$age)        # vypíše 53

# další způsob vyčítání

print(my_list[["firstName"]])  # vypíše Josef
print(my_list[["age"]])        # vypíše 53

# u tohoto způsobu vyčítání však můžeme využít i vyčítání pomocí pozice
# (přistupuj k tomu jako kdyby to byl vektor, způsob je stejný, akorát se to jinak zapisuje)

print(my_list[[1]])  # vypíše Josef  (protože Josef je napsané v listu na 1. pozici)
print(my_list[[3]])  # vypíše 53     (protože 53 je napsané v listu na 3. pozici)
```
```r
# příklad editace, předpokládejme předchozí deklaraci

print(my_list$firstName)      # vypíše Josef
my_list$firstName <- "Jirka"  # zapíše do firstName Jirka
print(my_list$firstName)      # vypíše Jirka
```

*Tady je příklad složitějšího použití listu:*
```r
questions <- list(
  list(
    text = "y = x^3+3, derivuj y",
    options = list(
      list(text = "3x^2", correct = TRUE),
      list(text = "2x^2+3x", correct = FALSE),
      list(text = "(x^4)/4+3x", correct = FALSE),
      list(text = "2x^2", correct = FALSE)
    )
  ),
  list(
    text = "y = 6x+2, integruj y",
    options = list(
      list(text = "6+2x", correct = FALSE),
      list(text = "3x^2+2x", correct = TRUE),
      list(text = "6x^2+2x", correct = FALSE),
      list(text = "2x^3+2x", correct = FALSE)
    )
  )
)
```
*Toto jsou 3 vnořené listy do sebe, ten vnější nemá žádnou identifikaci slovy, tedy budeme nuceni použít identifikaci pomocí pozice*
```r
# pokud bych chtěl text 1. otázky:

print(list[[1]]$text)   # vypíše y = x^3+3, derivuj y

# pokud bych chtěl pravdivost 3. odpovědi u 2. otázky

print(list[[2]]$options[[3]]$correct) # vypíše FALSE

# pokud bych chtěl text 1. odpovědi u 2. otátzky

print(list[[2]]$options[[1]]$text)  # vypíše 6+2x
```
___
## Podmíky
*Používáme je, aby se program mohl rozhodnout na základně nějakých informací*

*U podmínek využíváme [relační operátory](#Relační-operátory) a [logické operátory](#Logické-operátory)*.
```r
# Chceme dělit dvě čísla, ale nevíme, zda by se ve jmenovateli nemohla vyskytnout 0
# proto zavedeme podmínku, kterou to ošetříme

a <- 5
b <- 0

if (b != 0) {
  print(a/b)
} else {
  print("Dělení nulou")
}
```
```r
# Chceme vědět, jestli je a sudé
# tedy zavedeme podmínku:

a <- 7
if (a %% 2 == 0) {
  print(paste(a,"je sudé"))
} else {
  print(paste(a,"je liché"))
}
```
```r
# Máme číslo, které je zadávané uživatelem a chceme ho udržet v nějakých mezích
# tedy zavedeme podmínku pro udělání rozsahu 0-10:

a = 12 # to je to co zadal ten uživatel
if (a >= 0 && a <= 10) {
  print(paste(a,"je v rozsahu 0-10"))
} else {
  print(paste(a,"je mimo rozsah 0-10"))
}
```

```r
# Další příklad:

prvek <- list(nazev="kyslík", skupenstvi="plynné")

if (prvek$skupenstvi == "pevné") {
  print(paste(prvek$nazev, "je skladován v boxu"))
} else if (prvek$skupenstvi == "plynné") {
  print(paste(prvek$nazev, "je skladován v bombě"))
} else if (prvek$skupenstvi == "kapalné") {
  print(paste(prvek$nazev, "je skladován v nádobě"))
} else {
  print("Plazmu nikde neskladujeme")
}
```


___
## Cykly
*Jsou velmi potřebné, zvláště, když pracujeme s pokročilejšími datovými typy viz. [pokročilé datové typy](#Pokročilé-datové-typy)*

*Máme dva typy cyklů a to:*
- while loop
- for loop

*Cykly používáme, když potřebujeme něco procházet a tím pádem měnit pozici, sčítat/odčítat hodně prvků, nebo cokoli co potřebujeme vykonat několikrát. Využití je spoustu, proto vřele doporuřuji se na tohle společně s [pokročilými datovými typy](#Pokročilé-datové-typy) podívat. Porozumění těmto dvoum tématům je velmi důležité. 

### while loop
*K while cyklu je potřeba porozumět [podmínkám](#Podmínky)*
```r
# Takhle to vypadá
# while (podmínka) {}

my_number = 0
while (my_number < 4) {
  my_number = 1+number
  print(my_number)
}
```
*Toto vypíše do konzoli dohromady 4 řádky*
```r
1 # Toto byl první krok, kouklo se to na podmínku 0 < 4 což je pravda,
  # tedy se přičetla 1 k my_number a vypsal se tento řádek
2 # Tady to samé akorát podmínka byla 1 < 4 což je furt pravda
3 # Tady to samé akorát podmínka byla 2 < 4 což je furt pravda
4 # Tady to samé akorát podmínka byla 3 < 4 což je furt pravda

# Další řádek (tedy číslo 5) se ti už nevypíše protože 4 < 4 není pravda
```
*Je potřeba vnímat, že nejprve se koukneme na podmínku s nějakým číslem, potom pokud jsme podmínkou prošli k tomu číslu přičteme jedničku a až pak ho vypisujeme do konzoli. Tedy číslo zobrazené neodpovídá číslu, které bylo v rozhodovací podmínce. Z tohoto důvodu se nám vypsala 4 do konzoli*

*Víc se využívá cyklus for, protože většinou již dopředu víme, kolik průběhů cyklem potřebujeme. While se hodí pokud nevíme kolik průběhů bude*

*!! Bacha na nekonečný while cykly !!*

### for loop
*K while cyklu je potřeba porozumět [vektorům](#vector)*
```r
# Takhle to vypadá
# while (podmínka) {}

my_number = 0
while (my_number < 4) {
  my_number = 1+number
  print(my_number);
}
```
