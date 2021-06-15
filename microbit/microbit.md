# Oppgaver med micro:bit

Her finner du oppgaver for micro:bit. Du finner flere oppgaver med micro:bit og Bit:bot i [super:bit-oppdraget](https://github.com/oivron/komme-i-gang-microbit).

I oppgavene brukes **løkker**, **betingelser**, **variable**, **datatyper** (heltall og tekst), **str-funksjonen**, microbit-modulene **random**, **music** og **speech**.

## Oppgave 1: Terning

I denne oppgaven skal du bruke micro:bit til å lage en terning. Når terningen ristes, skal den vise antallet på micro:bit-skjemen og lese det med tekst-til-tale. Når terningen for eksempel viser 3, vil det stå 3 på skjermen samtidig som talesyntesen leser tallet på engelsk. Det finnes ingen norsk stemme. Tekst-til-tale på micro:bit er ikke ferdig utviklet og er ganske dårlig. Men det er morsomt å bruke den likevel.

<details>
<summary>Klikk for å utvide.</summary>

Utstyr: micro:bit, buzzer/hodetelefoner/høyttalere, ledninger.

1. Opprett en ny fil (**Ctrl+N**).
2. Lagre filen (**Ctrl+S**). Gi filen et navn (for eksempel terning.py).
3. micro:bit reagerer på bevegelse. Så i stedet for å kaste den, kan vi riste den. I oppgaven trenger du to ekstra moduler, nemlig speech og random. Legg import-setninger for de to modulene helt først i koden. Husk også selve micro:bit-modulen.
4. Vi vil at det skal være mulig å bruke terningen flere ganger. Da trenger du en løkke slik at programmet ditt kjører uendelig. Det kan du skrive slik:

```
    while True:
```

5. Inne i while-løkka trenger du en instruksjon som bestemmer hva som skal skje når micro:bit ristes (shake). Da passer det å bruke en if-setning. micro:bit reagerer på bevegelse fordi den har en bevegelsessensor (akselerometer). Koden du trenger ser slik ut:

```
    if accelerometer.was_gesture("shake"):
```

6. For å få et tilfeldig tall fra 1 til 6, passer det å bruke randint fra modulen random. Og så trenger du en variabel. En variabel brukes til å lagre verdier, for eksempel et tall. En variabel har et passende navn som du bestemmer selv, og en verdi. Her passer det å kalle variabelen for antall. Du trenger en instruksjon som lager et tilfeldig tall mellom 1 og 6, og som lagrer det i variabelen antall:

```
    antall = random.randint(1, 6)
```

7. Så skal du sørge for at det tilgfeldige tallet leses opp av micro:bit. Nå trenger du modulen speech. Instruksjonen du skal bruke ser slik ut:

```
    speech.say(str(antall))
```

8. Legg merke til at du må bruke funksjonen str på variabelen antall. Dette kommer av at variabler kan lagre ulike typer data, for eksempel tekst og tall. Typen som variabelen antall lagrer, er tall. Men det vi skal få lest opp med talesyntesen, må være av typen tekst. Så du må bruke funksjonen str for å gjøre om variabelen antall fra tall til tekst.

9. Det siste du skal gjøre er å vise variabelen antall på LED-matrisen. Det er en ganske grei instruksjon og den ser slik ut:

```
    display.show(antall)
```

10. Husk innrykk, både i while-løkka og i if-setningen!
11. Lagre endringene (**Ctrl+S**) og gå til Terminal (**Ctrl+Ø**). Kjør programmet ditt.

### Løsningsforslag

<details>
<summary>Klikk for å utvide.</summary>

```
from micro:bit import *
import speech
import random

while True:
  if accelerometer.was_gesture("shake"):
    antall = random.randint(1, 6)
    speech.say(str(antall))
    display.show(antall)
```

</details>
</details>
&nbsp; 

## Oppgave 2 Gangespill

I denne oppgaven skal du lage et gangespill som kan gange to tall. Når du rister microbit skal du få beskjed om å gange to tall mellom 1 og 9. Du skal så svare ved å angi tierne med å trykke knapp A og enerne ved å trykke på knapp B. Hvis du får beskjed om å gange 3 og 9 (som er 27), skal du trykke 2 ganger på knapp A og 7 ganger på B. For å sende svaret, skal du snu microbit opp ned. Du skal så få beskjed om du svarte riktig eller galt.

<details>
<summary>Klikk for å utvide.</summary>

Utstyr: micro:bit, buzzer/hodetelefoner/høyttalere, ledninger.

Når microbit ristes, lager den to tilfeldige tall mellom 1 og 9. Disse tallene blir lagret i variablene faktor1 og faktor2. Variabelen produkt er faktor1 ganger faktor2, mens svar er svaret som du gir.

1. I tillegg til selve microbit-modulen, trenger du modulene random, speech og music til denne oppgaven. Start med å skrive alle import-setningene:
2. Du trenger en while-løkke slik at du kan spille spillet flere ganger. Den skal inneholde resten av programkoden du skal lage.
3. Deretter må du ha flere betingelser som dekker alle hendelsene (riste, trykke på knapp A, trykke på knapp B og snu opp ned). microbit skal gi oss to tall som skal ganges når vi rister den. Så den første betingelsen blir akkurat som i terning-oppgaven:

```
    if accelerometer.was_gesture("shake"):
```

4. Hva må du ha etter if-setningen? Det første du må gjøre, er å lage to variabler som skal ta vare på svaret du gir. Vi kaller dem enere og tiere. Du må si at de skal ha verdien 0. Det er viktig fordi vi må være sikre på at verdien nullstilles mellom hver gang vi spiller gangespillet.
5. Så trenger du to variabler som tar vare på de to tilfeldige tallene som microbit lager når vi rister den. Disse kaller vi faktor1 og faktor2:

```
    faktor1 = random.randint(1, 9)
    faktor2 = random.randint(1, 9)
```

6. Du trenger enda en variabel, en som tar vare på tallet vi får når faktor1 og faktor2 multipliseres. Du kan kalle variabelen produkt. Det blir denne variabelen som tar vare på det riktige svaret:

```
    produkt = faktor1 * faktor2
```

7. Det neste som skal skje, er at microbit gir beskjed om hvilke to tall som skal ganges (faktor1 og faktor2). Du skal lese det opp med tekst-til-tale. I tillegg kan du også vise det på skjermen hvis du vil. Ta derfor med en eller begge av de følgende instruksjonene:

```
    display.scroll(str(faktor1) + " x " + str(faktor2))
    speech.say(str(faktor1) + "times" + str(faktor2))
```

8. Instruksjonen med speech er litt mer avansert enn den du brukt tidligere. Her vil vi at den syntetiske talen skal lese begge de to faktorene med ordet "times" i mellom. Legg også merke til at begge faktorene må gjøres om fra tall til tekst med funksjonen str.
9. Nå skal du sørge for at det blir mulig å gi et svar. Du trenger en ny betingelse og kan bygge videre på if-setningen med elif. Som nevnt skal knapp A brukes til å gi tierne, mens B skal brukes til enerne. Så hvis svaret er 27, blir det 2 ganger på A og 7 ganger på B. Dette krever ikke så mye å programkode. Du kan bruke et elegant uttrykk der vi øker verdien på tierne med én for hver gang knapp A trykkes:

```
    elif button_a.was_pressed():
        tiere += 1
```

10. For enerne trenger du tilsvarende.
11. Nå må programmet sammenligne svaret fra spilleren med variabelen produkt som programkoden vår har tatt vare på. Og så må spilleren får beskjed om svaret var riktig eller galt. Dette kan du gjøre med en ny betingelse, altså elif på nytt. Tidligere har du brukt risting og trykk på knapp A eller B. Nå skal du bruke en annen bevegelse, nemlig å snu microbit opp ned (face down):

```
    elif accelerometer.was_gesture("face down"):
```

12. Hittil vet programmet hvor mange ganger spilleren har trykket på A og på B. Men spillet vet ennå ikke hva svaret er. Du trenger en variabel som tar vare på dette tallet. Riktig svar må bli antall ganger trykk på A ganger 10 + antall ganger trykk på B. Denne variabelen kan du kalle for svar


```
    svar = (tiere * 10) + enere
```

13. Legg merke til at det står parentes rundt uttrykket tiere * 10. Hvorfor det? Er det nødvendig?
14. Du må sammenligne variablene svar og produkt. Er de identiske, er svaret riktig. Hvis ikke, er svaret galt. Her skal du bruke både talesyntese og musikk for å gi beskjed til spilleren om det ble riktig eller galt. Du trenger to betingelser, if og else. I if-setningen skal du sammenligne variablene svar og produkt. Det kan vi gjøre ved bruk av to likhetstegn. Og vi bruker en else-setning når vi ikke trenger noen bestemt betingelse. If-setningen har en betingelse, nemlig at svar og produkt skal være like (det vil si riktig svar). Men hvis svaret ikke er riktig, så må det være galt. Derfor kan du bruke else og ikke elif:

```
    if svar == produkt:
        music.play(music.JUMP_UP)
        speech.say("Correct answer")
    else:
        music.play(music.WAWAWAWAA)
        speech.say("Wrong answer")
```

15. Skriv nå else-setningen på tilsvarende måte. I stedet for melodien JUMP_UP skal du bruke WAWAWAWAA. Og i stedet for teksten Correct answer skal du bruke Wrong answer.

Dette ble et ganske langt program med mange forskjellige instruksjoner. Husk riktig innrykk! Hvis ikke krasjer programmet.

### Løsningsforslag

<details>
<summary>Klikk for å utvide.</summary>

```
from microbit import *
import random
import speech
import music

while True:
    if accelerometer.was_gesture("shake"):
        enere = 0
        tiere = 0
        faktor1 = random.randint(1, 9)
        faktor2 = random.randint(1, 9)
        produkt = faktor1 * faktor2
        display.scroll(str(faktor1) + " x " + str(faktor2))
        speech.say(str(faktor1) + "times" + str(faktor2))
    elif button_a.was_pressed():
        tiere += 1
    elif button_b.was_pressed():
        enere += 1
    elif accelerometer.was_gesture("face down"):
        svar = (tiere * 10) + enere
        if svar == produkt:
            music.play(music.JUMP_UP)
            speech.say("Correct answer")
        else:
            music.play(music.WAWAWAWAA)
            speech.say("Wrong answer")
```

</details>
</details>
&nbsp; 
