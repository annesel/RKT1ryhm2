---
title       : Esimene kodutöö - osa 2
description : Esimene teema - vektorid
--- type:NormalExercise lang:r xp:100 skills:1 key:051769665f
## Muutujad 1

Ka kalkulaatorit kasutades tekib peatselt vajadus meeles pidada arvutuste tulemusi. R-is võivad muutujate nimed sisaldada suuri ja väikesi tähti, numbreid; punkti ja alakriipsu. Erandiks on see, et nimi ei või alata numbri või alakriipsuga. Näiteks saab omistada `x`-le väärtuse 3 järgmiselt: `x <- 3`. 

**Tähtis!** R teeb vahet suurte ja väikeste tähtede vahel. Seega on `x` ja `X` kaks erinevat objekti. Samuti annab `SQRT(2)` veateate, sest ruutjuure leidmise funktsioon on `sqrt()` (väikesed tähed!).


*** =instructions

- Proovi läbi näited 1 ja 2.
- **Ülesanne:** Loo muutuja `w` väärtusega 3 ning  omista muutujale `z` summa, mille liidetavad on `w` ja 5. Väljasta `z` väärtus ekraanile.


*** =hint

* Omistamiseks kasuta märki `<-`.
* Kasuta tehet `w + 5`.
* Väärtuse ekraanile väljastamiseks kirjuta lihtsalt selle muutuja nime `z`.

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

