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
1. Moodusta vektor `w`., milles on arvud $1, 2, \ldots, 250$.
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
msg_undefinedz = "Make sure to define a variable `z`."
msg_incorrectz = "Make sure that you assign the correct value to `z`."
test_object("z", 
            undefined_msg = msg_undefinedz,
            incorrect_msg = msg_incorrectz) 


msg_undefinedw = "Make sure to define a variable `w`."
msg_incorrectw = "Make sure that you assign the correct value to `w`."
test_object("w", 
            undefined_msg = msg_undefinedw,
            incorrect_msg = msg_incorrectw) 



success_msg("Good job!")



```





