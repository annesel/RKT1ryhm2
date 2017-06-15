---
title       : Esimene kodutöö
description : Esimese nädala ülesanded
--- type:NormalExercise lang:r xp:100 skills:1 key:07547c77c0
## Arvutamine


*** =instructions

Lahenda ülesanded

1. Omista arv $25 \pi$ muutujale `z`.
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
#                    not_typed_msg = "Kas kasutad teises ülesandes funktsiooni `log10` argumendina muutujat `z`?")

 
 
 
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





