---
title       : Esimene kodutöö
description : Esimese nädala ülesanded
--- type:NormalExercise lang:r xp:50 skills:1 key:07547c77c0
## Sissejuhatus

Kirjuta kõigi ülesannete lahendused paremal aknapoolell olevasse *script.R* lehele, vastava ülesande sõnastuse alla. Siinses näites on esimese ülesande vastus juba kirja pandud.

Ühe vastuse väljaarvutamiseks või testimiseks pane hiirekursor vastava rea peale ja vajuta klahvikombinatsiooni `Ctrl+Enter`, 
sellega saadetakse vastav rida allpool olevale R-i konsoolile täitmiseks. Konsooli käsurida võid ka kasutada: kirjuta käsk ning vajuta täitmiseks `Enter`-klahvi. Proovi siin need võimalused läbi.

Lahenduse vihjete saamiseks vajuta nuppu `Take Hint`, aga sellega kaotad punkte!

Kui **kõik** lahendused on kirjas vajuta `Submit Answer`-nuppu, sellega oled ülesanded esitanud. 


*** =instructions
**Prooviülesanne:**

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
test_object("x", incorrect_msg = "Omistamine läks valesti. Proovi uuesti!")
success_msg("Tubli! Asu nüüd päris ülesandeid lahendama!")

```


<!------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------->

--- type:NormalExercise lang:r xp:100 skills:1 key:fe30c44601
## Arvutamine ja muutujate tekitamine

Kirjuta kõigi ülesannete lahendused paremal aknapaanil olevasse *script.R* lehele, vastava ülesande sõnastuse alla. 

Ühe vastuse väljaarvutamiseks või testimiseks pane hiirekursor vastava rea peale ja vajuta klahvikombinatsiooni `Ctrl+Enter`, 
sellega saadetakse vastav rida allpool olevale R-i konsoolile täitmiseks. Konsooli käsurida võid ka kasutada: kirjuta käsk ning vajuta täitmiseks `Enter`-klahvi.

Lahenduse vihjete saamiseks vajuta nuppu `Take Hint`, aga sellega kaotad võimalikke punkte!

Kui **kõik** lahendused on kirjas vajuta `Submit Answer`-nuppu, sellega oled ülesanded esitanud. 



*** =instructions
**Lahenda ülesanded:**

1. Omista arv $25 \pi$ muutujale `z`. Arv $\pi$ on R-is muutuja `pi` nime all.
1. Leia arvu $25 \pi$ kümnendlogaritm, kasutades muutujat `z`.
1. Leia arvu $25 \pi$ naturaallogaritm, kasutades muutujat `z`.
1. Moodusta vektor `w`, milles on arvud $1, 2, \ldots, 250$.
1. Liida arvud ühest kuni 250-ni: $\sum_{i=1}^{250} i$, kasutades eelnevalt defineeritud vektorit $w$.




*** =hint
- Logaritmifunktsiooni abilehe saad avada kui kirjutad konsoolile `?log` ja vajutad enter-klahvi.
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
<!------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------->
<!------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------->


