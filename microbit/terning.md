## Oppgaver med micro:bit.

Her finner du oppgaver for micro:bit. Du finner flere oppgaver med micro:bit og Bit:bot i [super:bit-oppdraget](https://github.com/oivron/komme-i-gang-micro:bit).

### Oppgave 1 Terning

I denne oppgaven skal du bruke micro:bit til å lage en terning. I oppgaven brukes:
- Løkker
- Betingelser
- Variable
- Datatyper (heltall og tekst)
- str-funksjonen
- microbit-modulene random, speech

<details>
<summary>Klikk for å utvide.</summary>


Utstyr: micro:bit, buzzer/hodetelefoner/høyttalere, ledninger.

I denne oppgaven skal du lage en terning. Når terningen ristes, skal den vise antallet på micro:bit-skjemen og lese det med tekst-til-tale. Når terningen for eksempel viser 3, vil det stå 3 på skjermen samtidig som talesyntesen leser tallet på engelsk. Det finnes ingen norsk stemme. Tekst-til-tale på micro:bit er ikke ferdig utviklet og er ganske dårlig. Men det er morsomt å bruke den likevel.

Vi kan ikke kaste micro:biten slik vi kaster en terning. Men micro:bit reagerer på bevegelse, så i stedet kan vi riste den. For at vi skal kunne bruke både tekst-til-tale og bevegelse på micro:bit, trenger vi to ekstra moduler, nemlig speech og random. Vi legger import-setninger for de modulene vi trenger helt først i koden. Husk at du også trenger selve micro:bit-modulen.

Bruk en while-løkke slik at programmet ditt kjører uendelig:

```
while True:
```

Inne i while-løkka trenger du en instruksjon som sier noe om hva som skal skje hvis micro:bit ristes (shake). Da passer det å bruke en if-setning. Det at micro:bit reagerer på bevegelse, betyr at den har en bevegelsessensor eller et akselerometer. Koden du trenger ser slik ut:

```
if accelerometer.was_gesture("shake"):
```

Hva er det som skal skje når du rister micro:bit? Jo, vi vil at micro:bit skal velge et tilfeldig tall fra 1 til 6. Det er jo slik en terning virker. Nå kan du bruke de mulighetene som ligger i modulen random. Og så trenger du en variabel. En variabel brukes til å lagre verdier, for eksempel et tall. En variabel har et passende navn som du bestemmer selv, og en verdi. Her kan det passe bra å kalle variabelen for antall. Du trenger en instruksjon som lager et tilfeldig tall mellom 1 og 6, og som lagrer det i variabelen antall:

```
antall = random.randint(1, 6)
```

Koden din skal nå se omtrent slik ut:

```
from micro:bit import *
import speech
import random

while True:
  if accelerometer.was_gesture("shake"):
    antall = random.randint(1, 6)
```

Dette er all koden som skal til for å lage et tilfeldig tall mellom 1 og 6 når du rister micro:bit. Men hva er det som mangler? Jo, du må sørge for at tallet leses opp og vises på micro:bit. Nå trenger du modulen speech. For at micro:bit skal lese opp tallet med tekst-itl-tale, kan du bruke instruksjonen:

```
speech.say(str(antall))
```

Legg merke til at du må ha str foran variabelen antall. Dette kommer av at variabler kan lagre ulike typer data, for eksempel tekst og tall. Typen som variabelen antall lagrer, er tall. Men det vi skal få lest opp med talesyntesen, må være av typen tekst. Så du må bruke en funksjon som kalles str for å konvertere variabelen antall fra tall til tekst:

Det siste du skal gjøre er å vise variabelen antall på LED-matrisen. Det er en ganske grei instruksjon og den ser slik ut:


```
display.show(antall)
```

Husk at du må bruke innrykk, både i while-løkka og i if-setningen! Hele koden din skal nå se slik ut:

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


### Oppgave 2 Gangespill

I denne oppgaven skal du lage et spillsom kan gange to tall.

<details>
<summary>Klikk for å utvide.</summary>

Utstyr: micro:bit, buzzer/hodetelefoner/høyttalere, ledninger.

I denne oppgaven skal du lage et gangespill. Når du rister microbit skal du få beskjed om å gange to tall mellom 1 og 9. Du skal så svare ved å angi tierne med å trykke knapp A og enerne ved å trykke på knapp B. Hvis du får beskjed om å gange 3 og 9 (som er 27), skal du trykke 2 ganger på knapp A og 7 ganger på B. For å sende svaret, skal du snu microbit opp ned. Du skal så få beskjed om du svarte riktig eller galt.

I tillegg til selve microbit-modulen, trenger du modulene random, speech og music til denne oppgaven. Du må derfor starte programmet med flere import-setninger:

```
from microbit import *
import random
import speech
import music
```

Når microbit ristes, lager den to tilfeldige tall mellom 1 og 9. Disse tallene blir lagret i variablene faktor1 og faktor2. Variabelen produkt er faktor1 ganger faktor2, mens svar er svaret som du gir.

Du trenger en while-løkke slik at du kan spille spillet flere ganger. Den skal inneholde resten av programkoden du skal lage. Deretter må du ha flere betingelser som dekker alle hendelsene (riste, trykke på knapp A, trykke på knapp B og snu opp ned). microbit skal gi oss to tall som skal ganges når vi rister den. Så den første betingelsen blir akkurat som i terning-oppgaven:

```
while True:
    if accelerometer.was_gesture("shake"):
```

Hva må du ha etter if-setningen? Det første du må gjøre, er å lage to variabler som skal ta vare på svaret du gir. Vi kaller dem enere og tiere. Du må si at de skal ha verdien 0. Det er viktig fordi vi må være sikre på at verdien nullstilles mellom hver gang vi spiller gangespillet. Så trenger du to variabler som tar vare på de to tilfeldige tallene som microbit lager når vi rister den. Disse kaller vi faktor1 og faktor2. For å gjøre dette, skriver du

```
enere = 0
tiere = 0
faktor1 = random.randint(1, 9)
faktor2 = random.randint(1, 9)
```

Du trenger enda en variabel. Du må ha en som tar vare på tallet vi får når faktor1 og faktor2 multipliseres. Du kan kalle denne variabelen produkt. Det blir altså denne variabelen som tar vare på det riktige svaret. Men verdien får du ikke vite, den skal du gjette når du spiller spillet.

```
produkt = faktor1 * faktor2
```

Det neste som skal skje, er at spillet gir beskjed om hvilke to tall som skal ganges (faktor1 og faktor2). Det går an å vise dette både med LED-matrisen og med syntetisk tale. Du trenger ikke vise det på LED-matrisen, men du må bruke syntetisk tale. Ta derfor med en eller begge av de følgende instruksjonene

```
display.scroll(str(faktor1) + " x " + str(faktor2))
speech.say(str(faktor1) + "and" + str(faktor2))
```

Instruksjonen med speech er litt mer avansert enn den du brukt tidligere. Her vil vi at den syntetiske talen skal lese begge de to faktorene med ordet "and" i mellom. Legg også merke til at begge faktorene må gjøres om fra tall til tekst.
Så langt har du bestemt hva som skal skje når microbit ristes. Husk innrykk! Nå skal du sørge for at den som spiller kan gi et svar når spillet ber spilleren gange to tall. Dette blir en ny betingelse og vi må bygge videre på if-setningen med elif. Som vi sa til å begynne med, så skal knapp A brukes til å gi tierne, mens B skal brukes til enerne. Så hvis svaret er 27, blir det 2 ganger på A og 7 ganger på B. Dette krever ikke så mye å programkode. Du kan bruke et elegant uttrykk der vi øker verdien på tierne med én for hver gang knapp A trykkes. Skriv følgende

```
elif button_a.was_pressed():
    tiere += 1
```

For enerne trenger du en tilsvarende setning

```
elif button_b.was_pressed():
        enere += 1
```

Så langt har spilleren fått beskjed om å gange to tall, og har svart ved å trykke et visst antall gang er på A og B.
Nå må programmet sammenligne svaret fra spilleren med variabelen produkt som programkoden vår har tatt vare på. Og så må spilleren får beskjed om svaret var riktig eller galt. Dette kan du gjøre med en ny betingelse, så vi bruker elif på nytt. Tidligere har vi brukt risting og trykk på knapp A eller B. Nå skal du bruke en annen bevegelse, nemlig å snu microbit opp ned.
Hittil vet programmet hvor mange ganger spilleren har trykket på A og på B. Men spillet vet ennå ikke hva svaret er. Vi trenger en variabel som tar vare på dette tallet. Riktig svar må bli antall ganger trykk på A ganger 10 + antall ganger trykk på B. Denne variabelen kan du kalle for svar
elif accelerometer.was_gesture("face down"):

```
    svar = (tiere * 10) + enere
```

Legg merke til at det står parentes rundt uttrykket tiere * 10. Hvorfor det? Er det nødvendig?
Det er nødvendig med noen flere instruksjoner. Du må sammenligne variablene svar og produkt. Er de identiske, er svaret riktig. Hvis ikke, er svaret galt. Her skal du bruke både talesyntese og musikk for å gi beskjed til spilleren om det ble riktig eller galt. Du trenger to betingelser, if og else. I if-setningen skal vi sammenligne variablene svar og produkt. Det kan vi gjøre ved bruk av to likhetstegn. Og vi bruker en else-setning når vi ikke trenger noen bestemt betingelse. If-setningen har en betingelse, nemlig at svar og produkt skal være like. Det vil altså si at spilleren har svart riktig. Men hvis svaret ikke er riktig, så må det være galt. Derfor kan du bruke else og ikke elif. Skriv derfor følgende instruksjoner

```
if svar == produkt:
    music.play(music.JUMP_UP)
    speech.say("Correct answer")
else:
    music.play(music.WAWAWAWAA)
    speech.say("Wrong answer")
```

Dette ble et ganske langt program med mange forskjellige instruksjoner. Husk riktig innrykk! Hvis ikke krasjer programmet. Hele programmet ditt skal nå se omtrent slik ut

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
        speech.say(str(faktor1) + "and" + str(faktor2))
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
