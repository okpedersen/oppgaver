---
title: Tekststrenger 2
level: 2
Author: Ole Kristian Pedersen, Kodeklubben Trondheim
---

# Introduksjon {.intro}

I denne oppgaven skal vi gå videre fra
[Tekststrenger 1](../tekststrenger_1/tekststrenger_1.md). Dersom du ikke har
gjort den er det anbefalt å gjøre den først.

# strip() {.activity}

# {.protip}

`s.strip()` fjerner all **whitespace** på høyre og venstre side av tekststrengen
`s`. Whitespace er "blanke tegn", altså tegn vi ikke ser, for eksempel
`" "` (mellomrom), `"\t"` (tab) og `"\n"` (linjeskift).  Dette er nyttig
for eksempel når man skal få inn input fra brukeren av programmet. Se på
følgende eksempel:

```python
>>> answer = " ja"  # Legg merke til at det er et ekstra mellomrom!
>>> answer == "ja"
False
```

Vi ser at vi ikke klarer å få rett resultat, selv om brukeren skrev `"ja"`.
Vi prøver oss med `s.split()`:

```python
>>> answer = " ja"
>>> answer.strip() == "ja"
True
```

Ofte vil vi gjøre mer med strengene enn å bare fjerne whitespace. Det kan
for eksempel være at vi ønsker å la brukeren ta inn både store og små
bokstaver i svaret sitt. Da kan vi bruke `s.upper()` eller `s.lower()`
sammen med `strip()`.

Det ville være naturlig å prøve noe som dette:

```python
>>> answer = " jA "
>>> answer = answer.strip()
>>> answer = answer.lower()
>>> answer == "ja"
True
```

Selv om eksempelet over ikke er galt, så finnes det en mye enklere måte å
gjøre det på:

```python
>>> answer = " jA "
>>> answer = answer.strip().lower()
>>> answer == "ja"
True
```

Vi kan til og med skrive det slik:

```python
>>> answer = " jA "
>>> answer.strip().lower() == "ja"
True
```

Dette kan vi gjøre, fordi alle funksjonene **returnerer** den manipulerte
strengen, istedenfor å endre på variabelen.

<!--Workaround-->
# {.check}

Vi vil nå skrive et program som skriver ut en og en gjenstand i ei liste, så
lenge brukeren ikke skriver `"stop"`. Du må ta hensyn til at det kan være
ekstra whitespace eller at det er både store og små bokstaver. Det kan se slik ut når det kjøres:

<pre>
>>>
Ada
<font color="green">neste</font>
Per
<font color="green">Brukeren kan skrive (nesten) hva som helst</font>
Kim
<font color="green">      StOP</font>
</pre>

Dette du må gjøre:

 * Lag ei liste, og fyll denne med noen ord
 * Bruk ei `for`-løkke for å gå igjennom hvert element i lista
    * Skriv ut elementet
    * Hent input fra brukeren
    * Hvis brukeren skrev inn `"stop"` (husk på store og små bokstaver,
      samt whitespace), skal du avbryte `for`-løkka (**hint:** `break`)

# Oppdeling og sammenslåing av strenger {.activity}

# split() {.protip}

`s.split()` er en nytting funksjon som lar oss dele opp strenger. Tenk deg
at du har en setning i en tekststreng og ønsker å finne hvert enkelt ord,
hadde det ikke vært greit å ha en funksjon som gjør det for deg?

```python
>>> "Dette er en setning".split()
['Dette', 'er', 'en', 'setning']
```

Når vi ikke gir et argument til `s.split()` vil den dele opp tekststrengen der
det er whitespace. Vi kan også dele på andre strenger:

```python
>>> "Per og Ada og Kim".split(" og ")
['Per', 'Ada', 'Kim']
```

<!--Workaround-->
# {.check}

Du skal skrive et program som får inn en tekststreng fra brukeren og skriver
ut hvert ord på en linje for seg selv. Slik skal det fungere:

<pre>
Skriv inn en tekststreng: <font color="green">Kim, Ada og Per.</font>
Kim,
Ada
og
Per.
</pre>

# Nyttig å vite {.try}

Hva skjer om du kjører denne koden? (**Hint:** Se på hvor mange tekstrenger
som er i lista du får ut.)

```python
>>> "Setning en. Setning 2.".split('.')
```

Hvorfor er det slik?

Dersom du ikke skjønner hvorfor er det lurt å snakke med en veileder.

# join() {.protip}

Vi kan bruke `s.join()` for å slå sammen strenger. Den fungerer "motsatt" av
`s.split()`. Den gis ei liste av teksstrenger som argument, og setter
ordene i lista sammen med tekstrengen `s` imellom. Dette er lettere å forstå
med et eksempel:

```python
>>> text = ";".join(["Per", "Ada", "Kim"])
>>> print(text)
Per;Ada;Kim
```

Vi ser at ordene i lista er satt sammen med ett semikolon imellom (`;`). Det
finnes mange andre måter å sette sammen ordene på:

```python
>>> text = " og ".join(["Per", "Ada", "Kim"]) # Sammenslåing med " og "
>>> print(text)
Per og Ada og Kim
```

```python
>>> text = "\n".join(["Per", "Ada", "Kim"])  # Hvert ord på egen linje
>>> print(text)
Per
Ada
Kim
```

<!--Workaround-->
# {.check}

Du skal nå skrive et program der du bytter ut all whitespace med et en
bindestrek (`-`). Dette må du gjøre ved hjelp av `s.split()` og `s.join()`.

<pre>
>>>
Skriv inn en tekststreng: <font color="green">Hei på deg!</font>
Hei-på-deg!
</pre>

Dette må du gjøre:

 * Spør brukeren om en tekststreng.
 * Del opp tekststrengen der det er whitespace, og lagre det i ei ny liste.
 * Slå sammen strengene i lista med en bindestrek mellom.
 * Skriv ut den nye strengen.

# Erstatte tekst {.activity}
