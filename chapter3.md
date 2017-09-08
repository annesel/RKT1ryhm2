---
title       : Esimene kodutöö - osa 3
description : Kolmas teema - vektorid, väärtuste tüübid
--- type:NormalExercise lang:r xp:100 skills:1 key:fead53a9da
## Vektorid 1

- Üksikuid arve või tekstiväärtusi saab kokku panna vektoriks funktsiooni `c()` (*combine*) abil. 
- Veel võimalusi vektorite moodustamiseks:
    * `1:5                 # arvujada 1, 2, 3, 4, 5`
    * `rep(1:3, times = 2) # vektorit elementidega 1, 2, 3 korrata 2 korda`
    * `seq(3, 9, by = 2)   # arvujada sammuga 2: 3, 5, 7, 9`
- Kui teha vektorobjektidega arvtusi, siis tehted tehakse läbi iga vektori elemendiga.

*** =instructions
- Tee läbi näited 1 kuni 3.
- **Ülesanne 1.** Teisenda temperatuurid celsiuse skaalalt fahrenheiti skaalale ($F^o = C^o \frac{9}{5} + 32$). Omista tulemus muutujale `Fahrenheit` ja prindi see ekraanile.
- **Ülesanne 2.** Vektoris `lisa` on veel kaks õhutemperatuuri($C^o$). Prindi see vektor ekraanile.
- **Ülesanne 3.** Kasutades funkstiooni `c()` moodusta vektor nimega `temp2`, mille esimesed 9 elementi  on temperatuurid vektorist `temp` ja järgmised 2 temperatuurid vektorist `lisa`. Väljasta tulemus ekraanile.


*** =hint
- Funktsiooni `c()` saab lisaks üksikutest väärtustest vektori tegemisele kasutada ka olemasolevate vektorite kombineerimiseks: `c(vektor1, vektor2)`.

*** =pre_exercise_code
```{r}
lisa <- c(-24.9, -16.1)
names(lisa) <- c("Mustvee", "Keila")


```

*** =sample_code
```{r}
# Näide 1: Moodustame 2 vektorit, millest ühes on kirjas temperatuurid (20.01.2010 kell 10), teises ilmajaamad, kus need on mõõdetud :
temp <- c(-6.2, -12.9, -13.0, -15.4, -16.1, -16.9, -17.0, -19.6, -19.9)
jaam <- c("Ruhnu", "Kihnu", "Pakri", "Tallinn", "Pärnu", "Kunda", "Kuusiku", "Võru", "Jõgeva")            

# Näide 2: Väljastame tulemused ekraanile
temp; jaam

# Näide 3: Paneme temperatuuridele jaamanimed juurde ja vaatame tulemust
names(temp) <- jaam
temp

# Ülesanne 1: Teisenda temperatuurid celsiuse skaalalt fahrenheiti skaalale (asenda alakriips vajaliku tehtega) ja prindi tulemus ekraanile
Fahrenheit <- ___________________ 
Fahrenheit 

# Ülesanne 2. Prindi ekraanile vektor nimega 'lisa'


# Ülesanne 3. Moodusta nõutud kujul uus vektor, selleks asenda alakriipsud vajalike objektidega. Prindi tulemus ekraanile.
temp2 <- c(_____, _____) 
temp2

```

*** =solution
```{r}
# Näide 1: Moodustame 2 vektorit, millest ühes on kirjas temperatuurid (20.01.2010 kell 10), teises jaamad, kus need on mõõdetud :
temp <- c(-6.2, -12.9, -13.0, -15.4, -16.1, -16.9, -17.0, -19.6, -19.9)
jaam <- c("Ruhnu", "Kihnu", "Pakri", "Tallinn", "Pärnu", "Kunda", "Kuusiku", "Võru", "Jõgeva")            # NB! Kui jutumärgid unustada, otsib R vastava nimega objekte!

# Näide 2: Väljastame tulemused ekraanile
temp; jaam

# Näide 3: Paneme temperatuuridele jaamanimed juurde ja vaatame tulemust
names(temp) <- jaam
temp

# Ülesanne 1: Teisenda temperatuurid celsiuse skaalalt fahrenheiti skaalale (asenda alakriipsud vajaliku tehteda) ja prindi tulemus ekraanile
Fahrenheit <- temp * 9/5 + 32
Fahrenheit 

# Ülesanne 2: Prindi ekraanile vektor nimega 'lisa'
lisa

# Ülesanne 3: Moodusta nõutud kujul uus vektor, selleks asenda alakriipsud vajalike objektidega. Prindi tulemus ekraanile.
temp2 <- c(temp, lisa) 
temp2
```

*** =sct
```{r}
test_object("Fahrenheit", undefined_msg = "Muutuja `Fahrenheit` on kaduma läinud!", incorrect_msg = "Kontrolli, kas omistad muutujale `Fahrenheit` õige tehte.")
test_output_contains("Fahrenheit", times = 1, incorrect_msg = "Prindi vektor `Fahrenheit` ekraanile!")


test_predefined_objects("lisa",undefined_msg = "Oled vektori `lisa` kustutanud! Alusta uuesti.", incorrect_msg = "Muutuja `lisa` väärtused on muudetud! Alusta uuesti.")
test_output_contains("lisa", incorrect_msg = "Vektor `lisa` pole välja prinditud!")


test_object("temp2", undefined_msg = "Puudub vektor `temp2`. Proovi uuesti!", incorrect_msg = "Vektori `temp2` väärtus ei vasta nõutule!")
test_output_contains("temp2", incorrect_msg = "Vektor `temp2` pole välja prinditud!")

success_msg("Super! Liigu järgmise ülesande juurde.")

```







--- type:NormalExercise lang:r xp:100 skills:1 key:dd8c92ca90
## Vektorid 2

Väga sageli on tarvis vektorist kätte saada meile hetkel vajalikku alamosa. Vaatame paari võimalust vektorist elementide välja noppimiseks. 


*** =instructions
 - Tee  näited 1 kuni 3  ükshaaval läbi ja uuri tulemust.
 - **Ülesanne 1:** Vali temperatuurivektorist elemendid, mis on paarisarvulistel kohtadel (paarisarvulise vektori moodustamiseks kasuta funktsiooni `seq()`). Omista saadud alamvektor muutujale `vastus1`. Prindi tulemus ekraanile.
 - **Ülesanne 2:** Vali välja jaamad, kus temperatuur on olnud -17 või alla selle. Kasuta valiku tegemisel tõeväärtusvektorit ja kandilisi sulge `[]`. Omista saadud alamvektor muutujale `vastus2`.  Prindi tulemus ekraanile.



*** =hint
- Funktsioonis `seq()` peab määrama argumendid `from`, `to` ja `by`.
- Märgi $\leq$ moodustamiseks kombineeri `<` ja `=` märke:  `<=`.

*** =pre_exercise_code
```{r}
temp <- c(-6.2, -12.9, -13.0, -15.4, -16.1, -16.9, -17.0, -19.6, -19.9)
jaam <- c("Ruhnu", "Kihnu", "Pakri", "Tallinn", "Pärnu", "Kunda", "Kuusiku", "Võru", "Jõgeva")          
```

*** =sample_code
```{r}
# Objektid nimedega temp ja jaam on töölaual juba olemas

# Näide 1. Elementide valimine indeksite kaudu
temp[ 1 ] # vektori esimene element
temp[ -1 ] # vektori kõik elemendid va esimene
temp[ c(1, 5, 9) ] # vektori esimene, viies ja üheksas element

# Näide 2. Tulemuseks tõeväärtustega vektorid 
temp < -15 # Kontrollime millised temperatuurid jäävad alla -15 kraadi 
jaam == "Tallinn"  # Millisel kohal vektoris on ilmajaama nimi Tallinn?

# Näide 3. Tingimustele vastavate elementide väljavalimine. Tõeväärtusvektori kasutamine
jaam[ temp < -15 ] # valime välja need  jaamad, kus temperatuur on alla -15
temp[jaam == "Tallinn"]  # valime välja Tallinnale vastava temperatuuri


# Ülesanne 1: Vali nõutud elemendid temperatuurivektorist, omista tulemus muutujale 'vastus1'. Prindi tulemus ekraanile
vastus1 <- temp[_______]
vastus1


# Ülesanne 2: Vali välja tingimusele vastavad ilmajaamade nimed, omista tulemus muutujale 'vastus2'. Prindi tulemus ekraanile
vastus2 <- ________
vastus2
```

*** =solution
```{r}
# Näide 1
temp[ 1 ] # vektori esimene element
temp[ -1 ] # vektori kõik elemendid va esimene
temp[ c(1, 5, 9) ] # vektori esimene, viies ja üheksas element

# Näide 2. Tulemuseks tõeväärtustega vektorid 
temp < -15 # Kontrollime millised temperatuurid jäävad alla -15 kraadi. 
jaam == "Tallinn"  # Mitmes jaam on Tallinn?

# Näide 3. Tingimustele vastavate elementide väljavalimine. Tõeväärtusvektori kasutamine
jaam[ temp < -15 ] # valime välja need  jaamad, kus temperatuur on alla -15
temp[jaam == "Tallinn"]  # valime välja Tallinnale vastava temperatuuri


# Ülesanne 1: Vali nõutud elemendid temperatuurivektorist, omista tulemus muutujale 'vastus1'. Prindi tulemus ekraanile
vastus1 <- temp[seq(2, 9, 2)]
vastus1


# Ülesanne 2: Vali välja tingimusele vastavad ilmajaamade nimed, omista tulemus muutujale 'vastus2'. Prindi tulemus ekraanile
vastus2 <- jaam[temp <= -17]
vastus2


```

*** =sct
```{r}
test_object("vastus1", undefined_msg = "Muutujat `vastus1` pole!", incorrect_msg = "Kontrolli, kas valid elemendid vektorist `temp` ja annad ette korrektsed indeksid?")
test_function("seq", args = c("from", "to", "by"), index = 1,
              eval = TRUE,
              eq_condition = "equivalent",
              not_called_msg = "Kasuta esimeses ülesandes indeksite määramiseks funktsiooni `seq()`!",
              args_not_specified_msg = "Kontrolli üle millised argumendid oled funktsioonile `seq()` andnud",
              incorrect_msg = "Funktsiooni `seq()` tulemus ei sobi! Proovi uuesti.")
test_output_contains("vastus1", incorrect_msg = "Vektor `vastus1` pole välja prinditud!")



test_object("vastus2", undefined_msg = "Muutujat `vastus2` pole!", incorrect_msg = "Kas moodustasid tõevektori kujul `temp <= -17`?")
test_output_contains("vastus2", incorrect_msg = "Vektor `vastus2` pole välja prinditud!")



success_msg("Tubli töö! Jätka samas vaimus!")
```










--- type:NormalExercise lang:r xp:100 skills:1 key:bcc48c5aea
## Väärtuste tüübid. Puuduvad väärtused
R-is on põhilised väärtuste tüübid, mida kasutame:

* `int` / `integer` -- täisarvud
* `numeric` -- reaalarvud
* `char` / `character` -- sõned (tähemärgid ja muud tekstilised sümbolid, sisestamisel kasutada jutumärke)
* `logical` -- tõeväärtused (ainult kaks väärtust: `TRUE` või `FALSE`)

Erisümbolid

* `NA` -- puuduv väärtus
* `NaN` -- määramatus
* `Inf`, `-Inf` -- lõpmatus
* 

Tüübi kontroll, teisendamine
* Objekti väärtuse tüübi kontrolliks saab kasutada funktsioone kujul `is.<tüüp>`, näiteks `is.character(muutuja)`, `is.nan(muutuja)`.
* Tüübi teisenduseks aga funktsioone `as.<tüüp>`, näiteks `as.integer(muutuja)`.



*** =instructions

- Vaata üle millised vektorid etteantud koodi alguses moodustatakse.
- **Ülesanne 1**: Kontrolli, kas vektor `muutuja1` on loogilist tüüpi. Täienda etteantud koodi, pannes kirja kontrolliks sobiva funktsiooni nime.
- **Ülesanne 2**: Rakenda funktsiooni `is.nan()` teisele moodustatud vektroile `muutuja2`. Pane tähele, et funktsiooni tulemus on ka vektor.
- **Ülesanne 3**: Asenda vektoris `muutuja3` esimene element tühikuga, kasutades funktsiooni `is.na()` abi. Prindi muudetud vektor ekraanile.

*** =hint
- Esimeses ülesandes kasuta funktsiooni `is.logical()`.
- Selleks, et esimene element määrata tühikuks, peab elemendi `is.na(muutuja3)[1]` väärtuseks omistama `TRUE`.


*** =pre_exercise_code
```{r}

```

*** =sample_code
```{r}
# Moodustame mõned vektorid ja vaatame tulemust.
muutuja1 <- c("TRUE", "true",  "Tru", "FALSE", "F", "false", NA)
muutuja2 <- c(1:3, NA, 0, Inf - Inf)
muutuja3 <- 1:6
muutuja1; muutuja2; muutuja3



# Ülesanne 1: Kontrolli kas vektor muutuja1 on loogilist tüüpi(asenda alakriipis sobiva sõnega, et moodustuks õige funktsiooni nimi).
is.______(muutuja1)

# Ülesanne 2: Rakenda funktsiooni is.nan() vektorile muutuja2.


# Ülesanne 3: Asenda vektori muutuja3 esimene element puuduva väärtusega, selleks asenda järgmises käsus alakriipis sobiva tõeväärtusega. Prindi tulemus ekraanile.
is.na(muutuja3)[1] <- _________
muutuja3


```

*** =solution
```{r}
# Moodustame mõned vektorid ja vaatame tulemust.
muutuja1 <- c("TRUE", "true",  "Tru", "FALSE", "F", "false", NA)
muutuja2 <- c(1:3, NA, 0, Inf - Inf)
muutuja3 <- 1:6
muutuja1; muutuja2; muutuja3


# Ülesanne 1: Kontrolli kas objekt muutuja1 on loogilist tüüpi(asenda alakriipis sobiva sõnega, et moodustuks õige funktsiooni nimi).
is.logical(muutuja1)


# Ülesanne 2: Rakenda funktsiooni is.nan() objektile muutuja2.
is.nan(muutuja2)

# Ülesanne 3: Asenda objekti muutuja3 esimene element puuduva väärtusega, selleks asenda alakriipis sobiva tõeväärtusega. Prindi tulemus ekraanile.
is.na(muutuja3)[1] <- TRUE
muutuja3
```

*** =sct
```{r}
test_predefined_objects("muutuja1",undefined_msg = "Oled vektori `muutuja1` kustutanud! Alusta uuesti.", incorrect_msg = "Muutuja `muutuja1` väärtused on muudetud! Alusta uuesti")
test_predefined_objects("muutuja2",undefined_msg = "Oled vektori `muutuja2` kustutanud! Alusta uuesti.", incorrect_msg = "Muutuja `muutuja2` väärtused on muudetud! Alusta uuesti")


test_function("is.logical",  args = "x", index = 1,
              eval = TRUE,
              eq_condition = "equivalent",
              not_called_msg = "Esimeses ülesandes kasuta funktsiooni `is.logical()`",
              args_not_specified_msg = NULL,
              incorrect_msg = "Esimeses ülesandes on funktsioonile `is-logical()` ette antud vale argumendiväärtus. Alusta uuesti.")



test_function("is.nan",  args = "x", index = 1,
              eval = TRUE,
              eq_condition = "equivalent",
              not_called_msg = "Teises ülesandes kasuta funktsiooni `is.nan()`",
              args_not_specified_msg = NULL,
              incorrect_msg = "Teises ülesandes on funtsioonile `is.nan()` ette antud vale argumendiväärtus. Alusta uuesti.")




test_function("is.na",  args = "x", index = 1,
              eval = TRUE,
              eq_condition = "equivalent",
              not_called_msg = "Viimases ülesandes kasuta funktsiooni `is.na()`",
              args_not_specified_msg = NULL,
              incorrect_msg = "Viimases ülesandes on funtsioonile ette antud vale argumendiväärtus. Alusta uuesti.")
test_object("muutuja3", undefined_msg = "Objekti `muutuja3` pole!", incorrect_msg = "Kas tegid omistamise kujul `is.na(muutuja3)[1] <- TRUE`?")

test_output_contains("muutuja3", incorrect_msg = "Vektor `muutuja3` pole välja prinditud!")


```