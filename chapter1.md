---
title       : Esimene kodutöö - osa 1
description : Esimene teema - kalkulaator, omistamine
--- type:NormalExercise lang:r xp:0 skills:1 key:07547c77c0
## Sissejuhatus

Kirjuta kõigi ülesannete lahendused paremal aknapoolel olevasse *script.R* lehele, vastava ülesande sõnastuse alla. Siinses näites on esimese ülesande lahendus juba kirja pandud.

Ühe vastuse väljaarvutamiseks või testimiseks pane hiirekursor vastava rea peale ja vajuta klahvikombinatsiooni `Ctrl+Enter`, 
sellega saadetakse vastav rida allpool olevale R-i konsoolile täitmiseks. Konsooli käsurida võid ka kasutada: kirjuta käsk ning vajuta täitmiseks `Enter`-klahvi. Proovi siin ülesandes need võimalused läbi.

Lahenduse vihjete saamiseks vajuta nuppu `Take Hint`, aga sellega kaotad võimalikke punkte! Kui oled lahti teinud vihjed, siis võid edasi avada ka kogu lahenduse koodi, kuid nii toimides lähevad ülesande punktid nulli.

Oma vastuse esitamiseks vajuta `Submit Answer`-nuppu, siis saadetakse ülesanded kontrollimiseks. Vajuta seda nuppu siis kui oled kirja pannud **kõik** selle lehekülje ülesannete vastused.


*** =instructions
**Prooviülesanne (0 punkti):**

1. Liida arvud 3 ja 4.
2. Omista väärtus 7 muutujale `x`.


*** =hint
- Liitmiseks kasuta märki `+` või funktsiooni `sum`
- Omistamiseks kasuta kombinatsiooni `<-`

*** =pre_exercise_code
```{r}
# pole midagi
```

*** =sample_code
```{r}
# Liida
3 + 4


# Omista
```



*** =solution
```{r}
# Liida
3 + 7

# Omista
x <- 7

```

*** =sct
```{r}
# esimene
test_output_contains("3+4", incorrect_msg = "Oled esimeses ülesandes õige vastuse valeks parandanud. Alusta uuesti!")


# teine
test_object("x",  undefined_msg = "Vali muutuja nimeks `x`.",  incorrect_msg = "Omistasid muutujale vale väärtuse. Proovi uuesti!")
success_msg("Tubli! Asu nüüd päris ülesandeid lahendama!")

```


<!--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------->

--- type:NormalExercise lang:r xp:100 skills:1 key:0f25fc4161
## Arvutamine

Esmalt mõned lihtsad arvutusülesanded. 

Meeldetuletuseks tehtemärgid:

- Liitmine: `+`
- Lahutamine: `-`
- Korrutamine: `*`
- Jagamine: `/`
- Astendamine: `^` või `**`
- Jääk jagamisel: `%%`

ja paar funktsiooni:

- Siinus: `sin()`
- Naturaallogaritm: `log()`
- Ruutjuur: `sqrt()`
- Eksponentfunkstioon `exp()`



*** =instructions
**Leia vastused järgmistele tehetele:**

1. $25 - 1:4  + 5:9$

1. $ (\sqrt{3} + 4) : 5 $

1. $ (245 - 3^6)^2 $

1. $ \frac{\sqrt{3} + 4}{55}$


*** =hint

*** =pre_exercise_code
```{r}

```

*** =sample_code
```{r}
# Ülesanne 1


# Ülesanne 2


# Ülesanne 3


# Ülesanne 4


```

*** =solution
```{r}
# Ülesanne 1
25 - 1/4  + 5/9

# Ülesanne 2
(sqrt(3) + 4) / 5

# Ülesanne 3
(245 - 3^6)^2 

# Ülesanne 4
(sqrt(3) + 4) / 55


```

*** =sct
```{r}
# Ül 2
#test_function_result(name = "sqrt",
#                     index = 2,
#                     eq_condition = "equivalent",
#                     not_called_msg = "Esimeses ülesandes pead kasutama funktsiooni `sqrt`",
#                     error_msg = "Esimeses ülesandes on midagi valesti!",
#                     incorrect_msg = "Oled esimeses funktsioonile `sqrt` andnud vale väärtusega argumendi")

#check_operator(state, name, index = 1, append = TRUE, not_called_msg = NULL)

#test_function(name = "sqrt",
#                     index = 1,
#                     eq_condition = "equivalent",
#                     not_called_msg = "Esimeses ülesandes pead kasutama funktsiooni `sqrt`",
#                     args_not_specified_msg = "Funktsioonile `sqrt` pole antud argumendi väärtust.",
#                     incorrect_msg = "Oled esimeses funktsioonile `sqrt` andnud vale väärtusega argumendi")
#test_output_contains(expr = "(sqrt(3) + 4) / 5",
#                    times = 1,
#                    incorrect_msg = "Midagi läks valesti! Kontrolli esimese ülesande vastust.")
 
 
#Ü1 1
test_output_contains(expr = "25 - 1/4  + 5/9 ",
                    times = 1,
                    incorrect_msg = "Midagi on esimeses ülesandes valesti! Kontrolli tehete järjekorda ja tehtemärke.")
 
# Ül 2
test_output_contains(expr = "(sqrt(3) + 4) / 5",
                    times = 1,
                    incorrect_msg = "Midagi on teises ülesandes valesti! Kontrolli tehete järjekorda. Ruutjuure leidmiseks kasuta `sqrt(3)`.")
# ÜL 3
test_output_contains(expr = "(245 - 3^6)^2 ",
                     times = 1,
                     incorrect_msg = "Midagi on komandas ülesandes valesti! Kontrolli tehete järjekorda. Astendamiseks kasuta märki `^` või `**`.")
 
# Ül 4
test_output_contains(expr = "(sqrt(3) + 4) / 55",
                     times = 1,
                     incorrect_msg = "Midagi on viimases ülesandes valesti! Kontrolli tehete järjekorda. Ruutjuure leidmiseks kasuta `sqrt(3)`.")
 
success_msg("Hästi! Mine edasi järgmise ülesande juurde.")


```

<!--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------->

--- type:NormalExercise lang:r xp:100 skills:1 key:fe30c44601
## Muutujate tekitamine ja kasutamine

R-is võivad muutujate nimed sisaldada suuri ja väikesi tähti, numbreid, punkti ja alakriipsu. Erandiks on see, et nimi ei või alata numbri või alakriipsuga. Näiteks saab omistada `x`-le väärtuse 3 järgmiselt: `x <- 3`. 



*** =instructions
**Lahenda ülesanded:**

1. Omista arv $25 \pi$ muutujale `z`. Arv $\pi$ on R-is muutuja `pi` nime all.

1. Leia arvu $25 \pi$ kümnendlogaritm, kasutades muutujat `z`.
 
1. Leia arvu $25 \pi$ naturaallogaritm, kasutades muutujat `z`.

1. Arvuta tehte $25 \pi + \frac{1}{25 \pi} - 2^{\frac{25\pi}{20}}$ vastus , kasutades muutujat `z`.

1. Moodusta vektor `w`, milles on arvud $1, 2, \ldots, 250$.

1. Liida arvud ühest kuni 250-ni: $\sum_{i=1}^{250} i$, kasutades eelnevalt defineeritud vektorit $w$.




*** =hint
- Logaritmifunktsiooni abilehe saad avada kui kirjutad konsoolile `?log` ja vajutad enter-klahvi.
- Kui sul tekkisid probleemid astendamismärgi `^` leidmisega, siis kasuta selle asemel `**`. 
- Väärtuseid  $1, 2, \ldots, 250$, sisaldava vektori moodustamiseks kasuta operaatorit `:` või käsku `seq`.
- Viimases ülesandes kasuta `sum` käsku.

*** =pre_exercise_code
```{r}

```

*** =sample_code
```{r}
# Omista muutujale z nõutud väärtus


# Leia muutuja z kümnendlogaritm


# Leia muutuja z naturaallogaritm


# Leia tehte vastus, kasutades muuutujat z


# Moodusta vektor w, milles on arvud 1, 2, ..., 250


# Liida arvud ühest kuni 250-ni, kasutades eelnevalt defineeritud vektorit w




```

*** =solution
```{r}
# Omista muutujale z nõutud väärtus
z <- 25*pi

# Leia muutuja z kümnendlogaritm
log10(z)

# Leia muutuja z naturaallogaritm
log(z)

# Leia tehte vastus
z + 1/z - 2^(z/20)


# Moodusta vektor w, milles on arvud 1, 2, ..., 250
w <- 1:250

# Liida arvud ühest kuni 250-ni, kasutades eelnevalt defineeritud vektorit w
sum(w)



```

*** =sct
```{r}
# esimene
msg_undefinedz = "Kontrolli, kas oled defineerinud muutuja `z`."
msg_incorrectz = "Kontrolli, kas oled muutujale `z` omistanud õige väärtuse."
test_object("z",  
            undefined_msg = msg_undefinedz,
            incorrect_msg = msg_incorrectz) 

 
# teine
test_function_result(name = "log10",
                     index = 1,
                     eq_condition = "equivalent",
                     not_called_msg = "Teises ülesandes pead kasutama funktsiooni `log10`",
                     error_msg = "Teises ülesandes on midagi valesti!",
                     incorrect_msg = "Oled funktsioonile `log10` andnud vale väärtusega argumendi")

 
test_output_contains(expr = "log10(z)",
                     times = 1,
                     incorrect_msg = "Midagi läks valesti! Kontrolli teise ülesande vastust.")
 
 
#test_student_typed("log10(z)",
#                    fixed = FALSE,
#                   not_typed_msg = "Kas kasutad teises ülesandes funktsiooni `log10` argumendina muutujat `z`?")

 
 
 
# kolmas
test_function_result(name = "log",
                     index = 1,
                     eq_condition = "equivalent",
                     not_called_msg = "Kolmandas ülesandes pead kasutama funktsiooni `log`",
                     error_msg = "Kolmandas ülesandes on midagi valesti!",
                     incorrect_msg = "Oled funktsioonile `log` andnud vale väärtusega argumendi")

test_output_contains(expr = "log(z)",
                     times = 1,
                     incorrect_msg = "Midagi läks valesti! Kontrolli kolmanda ülesande vastust.")
 
 
 
  
  
# neljas
msg_undefinedz = "Kontrolli, kas oled defineerinud muutuja `z`."
msg_incorrectz = "Kontrolli, kas oled muutujale `z` omistanud õige väärtuse."
#test_object("z",  
#            undefined_msg = msg_undefinedz,
#            incorrect_msg = msg_incorrectz) 
test_output_contains(expr = "z + 1/z - 2^(z/20)",
                     times = 1,
                     incorrect_msg = "Midagi läks valesti! Kontrolli neljanda ülesande tehte kirjapanekut.")
 
 

  
  
  
# neljas
msg_undefinedw = "Kontrolli, kas oled defineerinud muutuja `w`."
msg_incorrectw = "Kontrolli, kas oled muutujale `w` omistanud õige väärtuse."
test_object("w",  
            undefined_msg = msg_undefinedw,
            incorrect_msg = msg_incorrectw) 





# viies
test_function_result(name = "sum",
                     index = 1,
                     eq_condition = "equivalent",
                     not_called_msg = "Viimases ülesandes peaksid kasutama funktsiooni `sum`",
                     error_msg = "Viimases ülesandes on midagi valesti!",
                     incorrect_msg = "Oled funktsioonile `sum` andnud vale argumendi")

  
  
test_output_contains(expr = "sum(w)",
                     times = 1,
                     incorrect_msg = "Midagi läks valesti! Kontrolli viimase ülesande vastust.")
 
 
 


success_msg("Tubli!")
```


<!------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------->





--- type:NormalExercise lang:r xp:100 skills:1 key:bc9440a76a
## Tekstiväärtusega muutujad

Muutujad võivad olla ka tekstilised. Näiteks `x <- "Tere maailm!"` omistab muutujale `x` väärtuseks teksti `Tere maailm!`.
Tekstiväärtustega arvutustehteid teha ei saa, küll aga saab tekste omavahel ühendada funktsiooni `paste()` abil.



*** =instructions
- Proovi läbi näited 1 ja 2.
- Täida ka näite 3 käsud ja vaata, millise veateate annab R. Kas saad aru milles on viga?
- **Ülesanne:** paranda näite 3 koodi nii, et liitmisel tuleks vastuseks arv ning punast veateadet ei ilmuks.


*** =hint
Veendu, et oled muutnud koodi nii, et muutujale `poisse` omistatakse arvuline väärtus `3`: `poisse <- 3` ning muutujale `tydrukuid` arvuline väärtus 2: `tydrukuid <- 2`. 


*** =pre_exercise_code
```{r}

```

*** =sample_code
```{r}
# Näide 1: omistame muutujale `x` väärtuseks  teksti "Tere maailm!" ja väljastame selle
x <- "Tere maailm!"
x

# Näide 2: tekstide ühendamine, eri võimalusi
poisse <- "kolm"
tydrukuid <- "2"
paste(poisse, "ja", tydrukuid)
paste(poisse, tydrukuid)
paste(poisse, tydrukuid, sep = "")

# Näide 3: tekste ei saa liita, tulemuseks on veateade.
poisse <- "kolm"
tydrukuid <- "2"
lapsi <- poisse + tydrukuid
```

*** =solution
```{r}
# Näide 1: omistame muutujale `x` väärtuseks  teksti "Tere maailm!" ja väljastame selle
x <- "Tere maailm!"
x

# Näide 2: tekstide ühendamine, eri võimalusi
poisse <- "kolm"
tydrukuid <- "2"
paste(poisse, "ja", tydrukuid)
paste(poisse, tydrukuid)
paste(poisse, tydrukuid, sep = "")

# Näide 3: tekste ei saa liita, tulemuseks on veateade.
poisse <- 3
tydrukuid <- 2
lapsi <- poisse + tydrukuid
```

*** =sct
```{r}
test_object("poisse", incorrect_msg = "Kontrolli, kas omistad muutujale `poisse` arvu 3.")
test_object("tydrukuid", incorrect_msg = "Kontrolli, kas omistad muutujale `tydrukuid` arvu 2.")

msg <- "Kas kasutasid omistmiskäsku `lapsi <- poisse + tydrukuid`?"
test_object("lapsi", undefined_msg = msg, incorrect_msg = msg)
success_msg("Hästi tehtud! Suundu järgmise harjutuse juurde!")

```





--- type:NormalExercise lang:r xp:100 skills:1 key:fead53a9da
## Vektorid 1

- Üksikuid arve või tekstiväärtusi saab kokku panna vektoriks funktsiooni `c()` (*combine*) abil. 
- Veel võimalusi vektorite moodustamiseks:
    * `1:5                 # arvujada 1, 2, 3, 4, 5`
    * `rep(1:5, times = 2) # vektorit elementidega 1, 2, 3, 4, 5 korrata 2 korda`
    * `seq(2, 8, by = 2)   # arvujada sammuga 2: 2, 4, 6, 8`
- Kui teha vektorobjektidega arvtusi, siis tehted tehakse läbi iga vektori elemendiga.

*** =instructions
- Tee läbi näited 1 kuni 3.
- **Ülesanne 1.** Teisenda temperatuurid celsiuse skaalalt fahrenheiti skaalale, selleks korruta temperatuurid $\frac{9}{5}$ ja liida 32.
- **Ülesanne 2.** Kasutades operaatorit `:` moodusta vektor nimega `jada1`, mille elemendid on `5, 4, 3, 2, 1`. Väljasta tulemus ekraanile.
- **Ülesanne 3.** Kasutades funkstiooni `rep` moodusta vektor nimega `jada2`, mille elemendid on `"Ruhnu", "Kihnu", "Ruhnu", "Kihnu", "Ruhnu", "Kihnu"`. Väljasta tulemus ekraanile.


*** =hint
- Kasuta teises ülesandes funktsiooni `rep` esimese argumendina vektorit  `c("Ruhnu", "Kihnu")`.

*** =pre_exercise_code
```{r}

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

# Ülesanne 1: Teisenda temperatuurid celsiuse skaalalt fahrenheiti skaalale (asenda alakriipsud vajaliku tehteda) ja prindi tulemus ekraanile
Fahrenheit <- ___________________ #temp*9/5 + 32
Fahrenheit 

# Ülesanne 2. Asenda alakriipsud õigete väärtustega
jada1 <- __:__
jada1

# Ülesanne 32.  Asenda alakriipsud vajalike suurustega
jada2 <- rep(c(_____,_____), times = __)
jada2

```

*** =solution
```{r}
# Näide 1: Moodustame 2 vektorit, millest ühes on kirjas temperatuurid (20.01.2010 kell 10), teises jaamad, kus need on mõõdetud :
temp <- c(-6.2, -12.9, -13.0, -15.4, -16.1, -16.9, -17.0, -19.6, -19.9)
jaam <- c("Ruhnu", "Kihnu", "Pakri", "Tallinn", "Pärnu", "Kunda", "Kuusiku", "Võru", "Jõgeva")            # NB! Kui jutumärgid unustada, otsib R vastava nimega objekte!

# Näide 2: Väljastame tulemused 
temp; jaam

# Näide 3:  Tehted tehakse läbi kõigi vektori elementidega. Teisendame celsiuse skaalalt fahrenheiti skaalale
Fahrenheit <- temp*9/5+32
Fahrenheit 

# Ülesanne 1. Asenda alakriipsud õigete väärtustega
jada1 <- 5:1
jada1

# Ülesanne 2.  Asenda alakriipsud vajalike suurustega
jada2 <- rep(c("Ruhnu", "Kihnu"), times = 3)
jada2
```

*** =sct
```{r}
test_object("jada1", incorrect_msg= "Kas kasutasid `jada1` defineerimiseks käsku `5:1`?")
test_object("jada2", undefined_msg = NULL, incorrect_msg = "Muutuja `jada2` on defineeritud valesti. Proovi veel!")
success_msg("Super!")

```







--- type:NormalExercise lang:r xp:100 skills:1 key:dd8c92ca90
## ## Vektorid 2

Väga sageli on tarvis vektorist kätte saada meile hetkel vajalikku alamosa. Vaatame paari võimalust vektorist elementide välja noppimiseks. 




*** =instructions
 - Tee  näited 1 kuni 3  ükshaaval läbi ja uuri tulemust.
 - **Ülesanne:** vali välja jaamad, kus temperatuur on olnud -17 või alla selle. Kasuta tingimuse kirjapanekul märki $\leq$.

*** =hint
- Märgi $\leq$ moodustamiseks kombineeri `<` ja `=` märke:  `<=`.

*** =pre_exercise_code
```{r}
temp <- c(-6.2, -12.9, -13.0, -15.4, -16.1, -16.9, -17.0, -19.6, -19.9)
jaam <- c("Ruhnu", "Kihnu", "Pakri", "Tallinn", "Pärnu", "Kunda", "Kuusiku", "Võru", "Jõgeva")          
```

*** =sample_code
```{r}
# Näide 1
temp[ 1 ] # vektori esimene element
temp[ -1 ] # vektori kõik elemendid va esimene
temp[ c(1, 5, 9) ] # vektori esimene, viies ja üheksas element

# Näide 2. Tulemuseks tõeväärtustega vektorid 
temp < -15 # Kontrollime millised temperatuurid jäävad alla -15 kraadi. 
jaam == "Tallinn"  # Mitmes jaam on Tallinn?

# Näide 3. Tingimustele vastavate elementide väljavalimine
jaam[ temp < -15 ] # valime välja need  jaamad, kus temperatuur on alla -15
temp[jaam == "Tallinn"]  # valime välja Tallinnale vastava temperatuuri

# Ülesanne: asenda alakriipsud õige käsuga
vastus <- ________
vastus
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

# Näide 3. Tingimustele vastavate elementide väljavalimine
jaam[ temp < -15 ] # valime välja need  jaamad, kus temperatuur on alla -15
temp[jaam == "Tallinn"]  # valime välja Tallinnale vastava temperatuuri

# Ülesanne: asenda alakriipsud õige käsuga
vastus <- jaam[temp <= -17]
vastus
```

*** =sct
```{r}
test_object("vastus", undefined_msg = NULL, incorrect_msg = "Kas kasutasid käsku `jaam[temp <= -17]`?")
success_msg("Tubli töö! Jätka samas vaimus!")
```



--- type:MultipleChoiceExercise lang:r xp:100 skills:1 key:a1ac08c1e6
## Test 1. Küsimus 1.

Muutja `k` väärtuseks on `"kuusteist"` ja muutuja `m` väärtuseks on `4`. Millega võrdub `n <- k + m` väärtus? 

*** =instructions

- `"kakskümmend"`
- `20`
- tuleb veateade `Viga! Proovi veel!`
- tuleb veateade `Error: non-numeric argument to binary operator`

*** =hint
Vaata veelkord harjutust **Muutujad 2**.

*** =pre_exercise_code
```{r}

```

*** =sct
```{r}
# SCT written with testwhat: https://github.com/datacamp/testwhat/wiki

msg_bad <- "See pole õige vastus!"
msg_success <- "Täpselt! R ütleb, et proovid teha liitmistehet tekstiga."
test_mc(correct = 4, feedback_msgs = c(msg_bad,  msg_bad, msg_bad, msg_success))
```


--- type:MultipleChoiceExercise lang:r xp:100 skills:1 key:191cdeba71
## Test 1. Küsimus 2.

Loo vektor `esimene` elementidega 21-st kuni 60-ni sammuga 3 (vektori pikkus peab olema 14 elementi) ja teine vektor nimega `teine`, mille väärtused on `8, 9, 8, 9, 8, 9, 8, 9, 8, 9, 8, 9, 8, 9` . 
Vektorile `tulemus` omista väärtuseks nende vektorite vahe.

Millised vektori `tulemus` elemendid jaguvad 5-ga täpselt?


*** =instructions


- 2., 5. ja 12. element
- Kõik elemendid jaguvad 5-ga
- Ükski ei jagu
- 3. ja 6. element

*** =hint
Vaata veelkord harjutusi **R kui kalkulaator** (jäägi leidmine) ja **Muutujad 2** (vektorite moodustamine).

*** =pre_exercise_code
```{r}

```

*** =sct
```{r}
# SCT written with testwhat: https://github.com/datacamp/testwhat/wiki

msg_bad <- "See pole õige vastus!"
msg_success <- "Täpselt nii!"
test_mc(correct = 1, feedback_msgs = c(msg_success, msg_bad,  msg_bad, msg_bad))
```


