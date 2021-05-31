## Oppgaver med micro:bit.

Her finner du oppgaver for micro:bit. Du finner flere oppgaver med micro:bit og Bit:bot i [super:bit-oppdraget](https://github.com/oivron/komme-i-gang-microbit).

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

Husk at du må bruke innrykk, både i while-løkka og i if-setningen!

#### Løsningsforslag

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

### Oppgave 2 Gangespill

I denne oppgaven skal du lage et spill som kan gange to tall. I oppgaven brukes:
- Løkker
- Betingelser
- Variable
- Datatyper (heltall og tekst)
- Operatorer (multiplikasjon, inkrement, boolsk)
- str-funksjonen
- microbit-modulene random, speech, music

<details>
<summary>Klikk for å utvide.</summary>

Utstyr: micro:bit, høyttalere.

I denne oppgaven skal du lage et gangespill. Når du rister microbit skal du få beskjed om å gange to tall mellom 1 og 9. For å oppgi svar, skal du angi tierne ved å trykke knapp A og enerne ved å trykke på knapp B. Hvis du får beskjed om å gange 3 og 9 (som er 27), skal du trykke 2 ganger på knapp A og 7 ganger på B. For å sende svaret, skal du snu microbit opp ned. Du skal så få beskjed om du svarte riktig eller galt.

I tillegg til selve microbit-modulen, trenger du modulene random, speech og music til denne oppgaven. Du må derfor starte programmet med flere import-setninger:

```
from microbit import *
import random
import speech
import music
```

Du trenger en while-løkke slik at du kan spille spillet flere ganger. Den skal inneholde resten av programkoden du skal lage. Deretter må du ha flere betingelser som dekker alle hendelsene i programmet ditt (riste, trykke på knapp A, trykke på knapp B og snu opp ned). Spillet begynner ved at microbit gir deg to tall når du rister den. Du kan bruke metoden accelerometer.was_gesture for å finne ut om microbiten ristes. Så den første betingelsen inne i while-løkka blir:

```
while True:
    if accelerometer.was_gesture("shake"):
```

Hva må du ha inne i if-setningen? Hva skal skje når microbit ristes? Det første du trenger, er to variable som tar vare på de to tallene microbit lager når du rister den. Kall dem gjerne faktor1 og faktor2. Disse må så få en tilfeldig verdi mellom 1 og 9. Til det kan du bruke metoden random.randint:

```
faktor1 = random.randint(1, 9)
faktor2 = random.randint(1, 9)
```

Så trenger du to variabler som skal ta vare på svaret du gir, det vil si antall ganger du trykker på knapp A og antall ganger på knapp B. Du kan kalle dem tiere og enere. Dessuten må du si at tierne og enerne skal ha verdien 0 til å begynne med. Det er viktig fordi vi må være sikre på at verdien nullstilles mellom hver gang du spiller gangespillet. Hvordan skal du skrive dette i programmet ditt?

Du trenger enda en variabel. Du må ha en som tar vare på tallet du får når faktor1 og faktor2 ganges. Denne variabelen kan du kalle produkt. Siden Python er ganske god i matematikk, kan du enkelt regne ut det ved hjelpe av * (stjerne). Det blir altså variabelen produkt som tar vare på det riktige svaret. Hvordan skal du skrive dette uttrykket?

Det neste som skal skje, er at spillet gir beskjed om hvilke to tall som skal ganges (faktor1 og faktor2). Det går an å vise dette både på microbit-skjermen og med tekst-til-tale. Du trenger ikke vise det på skjermen hvis du ikke vil, men det kan kanskje være lurt hvis noen seende skal spille spillet du lager. Seende er ikke så flinke til å forstå tekst-til-tale. For å vise tallene på microbit-skjermen, bruker du metoden display.scroll. Men det er et problem. Du kan ikke vise faktor1 og faktor2 på skjermen siden de er av typen heltall. Du kan bare vise tekst. Så du må gjøre om fra heltall til tekst før du sender dem til skjermen. Til det kan du bruke en funksjon som heter str:

```
display.scroll(str(faktor1) + " x " + str(faktor2))
```

For å høre tallene med tekst-til-tale, bruker du metoden speech-say. Også her må du først gjøre om til tekst:

```
speech.say(str(faktor1) + "and" + str(faktor2))
```

Så langt har du bestemt hva som skal skje inne i den første if-setningen, altså når microbit ristes. Husk innrykk! Nå skal du sørge for at spilleren kan gi et svar når spillet ber spilleren gange to tall. Vi må bygge videre på if-setningen med elif. Som vi sa til å begynne med, så skal knapp A brukes til å angi tierne, mens B skal brukes til enerne. Så hvis svaret er 27, blir det 2 trykk på A og 7 på B. Dette krever ikke så mye å programkode. Hvilken metode må du bruke for å registrere antall ganger knapp A og B blir trykket? Du trenger en elif-setning for hver av dem. Antall trykk lagrer du i variablene tiere og enere. Det går an å skrive dette slik: tiere = tiere + 1. Det betyr at variablelen tiere skal være lik den gamle verdien av tiere pluss 1. Men i Python kan vi skrive dette veldig elegant slik:

```
tiere += 1
```

For enerne blir det tilsvarende. Så langt har spilleren fått beskjed om å gange to tall, og har svart ved å trykke et visst antall ganger er på A og B.

Nå må programmet sammenligne svaret fra spilleren med variabelen produkt. Og så må spilleren får beskjed om svaret var riktig eller galt. Dette kan du gjøre med en siste elif-setning. Tidligere har du brukt betingelser for risting og trykk på knapp A eller B. Nå skal du bruke en betingelse som dekker tilfellet med å snu microbit opp ned. Du kan bruke metoden accelerometer.was_gesture til dette:

```
elif accelerometer.was_gesture("face down")
```

Programmet vet allerede hvor mange ganger spilleren har trykket på knapp A og B (tiere og enere). Men spillet vet ennå ikke hva avgitt svar er. Du trenger en variabel som tar vare på dette tallet. Kall den gjerne svar. Hvordan kan du regne ut dette tallet.

Det er nødvendig med noen flere instruksjoner. Du må sammenligne variablene svar og produkt. Er de identiske, er svaret riktig. Hvis ikke, er svaret galt. Her skal du bruke både talesyntese og musikk for å gi beskjed til spilleren om det ble riktig eller galt. Du trenger to betingelser til dette, if og else. De må ligge inne i den siste elif-betingelsen du laget. I if-setningen skal vi sammenligne variablene svar og produkt. Det kan vi gjøre ved bruk av to likhetstegn (svar == produkt). Betingelsen er at svar og produkt er like. Det vil altså si at spilleren har svart riktig. Men hvis svaret ikke er riktig, så må det være galt. Derfor kan du bruke else og ikke elif. Bruk følgende kode og fyll ut det som skal være inne i else-betingelsen:


```
if svar == produkt:
    music.play(music.JUMP_UP)
    speech.say("Correct answer")
else:
    # Spill melodien WAWAWAWAA
    # La tekst-til-tale lese "Wrong answer"
```

Dette ble et ganske langt program med mange forskjellige instruksjoner. Husk riktig innrykk! Hvis ikke krasjer programmet.

#### Løsningsforslag

<details>
<summary>Klikk for å utvide.</summary>

```
from microbit import *
import random
import speech
import music

while True:
    if accelerometer.was_gesture("shake"):
        faktor1 = random.randint(1, 9)
        faktor2 = random.randint(1, 9)
        enere = 0
        tiere = 0
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
</details>
</details>
