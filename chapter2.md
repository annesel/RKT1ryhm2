---
title       : Esimene kodutöö - osa 2
description : Teine teema - muutujad
--- type:NormalExercise lang:r xp:100 skills:1 key:051769665f
## Muutujad 

R-is võivad muutujate nimed sisaldada suuri ja väikesi tähti, numbreid, punkti ja alakriipsu. Erandiks on see, et nimi ei või alata numbri või alakriipsuga. Näiteks saab omistada `x`-le väärtuse 3 järgmiselt: `x <- 3`. 

**Tähtis!** R teeb vahet suurte ja väikeste tähtede vahel. Seega on `x` ja `X` kaks erinevat objekti. Samuti annab `SQRT(2)` veateate, sest ruutjuure leidmise funktsioon on `sqrt()` (väikesed tähed!).




*** =instructions

- Proovi läbi näited 1 ja 2.
- **Ülesanne:** Loo muutuja `w` väärtusega 3 ning  omista muutujale `z` summa, mille liidetavad on `w` ja 5. Väljasta `z` väärtus ekraanile.


*** =hint

* Omistamiseks kasuta märki `<-`.
* Kasuta tehet `w + 5`.
* Väärtuse ekraanile väljastamiseks kirjuta lihtsalt selle muutuja nimi `z`.

*** =pre_exercise_code
```{r}

```

*** =sample_code
```{r}
# Näide 1. Omistame muutjale y väärtuse 2 ja väljastame väärtuse
y <- 2
y

# Näide 2. Kasutame muutujat y arvutuses
y + 5

# Ülesanne


```

*** =solution
```{r}
# Näide 1. Omistame muutjale y väärtuse 2 ja väljastame väärtuse
y <- 2
y

# Näide 2. Kasutame muutujat y arvutuses
y + 5

# Ülesanne
w <- 3
z <- w + 5
z

```

*** =sct
```{r}
test_object(c("w", "z"), undefined_msg = "Kontrolli muutujate nimesid, kas Sul on defineeritud muutujad `w` ja `z`?", incorrect_msg = "Kontrolli mõlema muutuja väärtust!")
test_student_typed("z <- w + 5", not_typed_msg = "Kas kirjutasid `z <- w + 5`?")
test_output_contains("z", incorrect_msg = "Kas kirjutasid viimasele reale `z`? ")
success_msg("Hästi tehtud!")
```




--- type:NormalExercise lang:r xp:100 skills:1 key:fe30c44601
## Muutujate kasutamine tehetes


*** =instructions
**Lahenda ülesanded:**

1. Omista arv $25 \pi$ muutujale `z`. Arv $\pi$ on R-is muutuja `pi` nime all.

1. Leia arvu $25 \pi$ kümnendlogaritm, kasutades muutujat `z`.
 
1. Leia arvu $25 \pi$ naturaallogaritm, kasutades muutujat `z`.

1. Arvuta tehte $25 \pi + \frac{1}{25 \pi} - 2^{\frac{25\pi}{19}}$ vastus , kasutades muutujat `z`.





*** =hint
- Logaritmifunktsiooni abilehe saad avada kui kirjutad konsoolile `?log` ja vajutad enter-klahvi.
- Kui sul tekkisid probleemid astendamismärgi `^` leidmisega, siis kasuta selle asemel `**`. 


*** =pre_exercise_code
```{r}

```

*** =sample_code
```{r}
# Omista muutujale z nõutud väärtus


# Leia muutuja z kümnendlogaritm


# Leia muutuja z naturaallogaritm


# Leia tehte vastus, kasutades muuutujat z




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
z + 1/z - 2^(z/19)




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
test_output_contains(expr = "z + 1/z - 2^(z/19)",
                     times = 1,
                     incorrect_msg = "Midagi läks valesti! Kontrolli neljanda ülesande tehte kirjapanekut.")
 
 


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

 
