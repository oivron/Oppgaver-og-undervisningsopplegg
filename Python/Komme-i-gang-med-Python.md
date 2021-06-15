# Komme i gang med programmering

Grunnleggende oppgaver i Python.

## Oppgave 1: Skriv navnet ditt

I denne oppgaven brukes **variable** og **if-setninger**, samt funksjonene **print** og **input**.

<details>
<summary>Klikk for å utvide.</summary>

Utstyr: Visual Studio Code.

### Deloppgave A

I denne deloppgaven skal du lage et lite program som skriver en melding på skjermen. Meldingen skal være fornavnet ditt.

<details>
<summary>Klikk for å utvide.</summary>

1. Opprett en ny fil (**Ctrl+N**).
2. Lagre filen (**Ctrl+S**). Gi filen et navn (for eksempel navn.py).
3. Den første instruksjonen du skal skrive, er en funksjon i Python som heter print. Den brukes for å skrive en melding på skjermen. I dette tilfellet er meldingen navnet ditt (for eksempel Anna). Etter print må selve meldingen stå mellom to parenteser. Og meldingen skal også omsluttes av anførselstegn:

```
   print("Anna")
```

4. Lagre filen (**Ctrl+S**).
5. Gå til Terminal i Visual Studio Code (**Ctrl+Ø**).
6. Skriv kommandoen for å kjøre programmet ditt. Du må skrive python etterfulgt av navnet på fila som inneholder programmet ditt:

```
   python navn.py
```

7. For å se hva programmet ditt skrev på skjermen, kan du bruke **Ctrl+Pil opp**. Ble det riktig?
8. Gå tilbake til programmet ditt med **Ctrl+1**.
9. Gjør en endring i programmet ditt slik at programmet i stedet skriver «Hei på deg» og så navnet ditt. For eksempel: «Hei på deg, Anna».

```
   print("Hei på deg, Anna")
```

10. Lagre endringene (**Ctrl+S**) og gå tilbake til Terminal (**Ctrl+Ø**). Kjør programmet på nytt:

```
   python navn.py
```

11. Gjorde programmet det det skulle?

</details>
&nbsp;  

### Deloppgave B

I denne deloppgaven skal du utvide programmet fra deloppgave A. Vi kan få programmet til å spørre etter navnet på den som skal kjøre programmet. Hun må da taste inn navnet sitt. Til slutt skal programmet skrive navnet på skjermen.

<details>
<summary>Klikk for å utvide.</summary>

1. Gå først tilbake til programmet ditt (**Ctrl+1**).
4. Først må du bruke en funksjon som heter input. Input bruker vi litt på samme måte som print, det vil si at vi trenger parenteser etter input og anførselstegn inne i parentesene. Når programmet inneholder input, vil programmet stoppe opp og vente på svar fra deg. Du må da skrive inn et svar og trykke Enter:

```
   input("Hva heter du?")
```

5. For at programmet ditt skal klare å ta vare på svaret du gir, må vi bruke noe som kalles en variabel. En variabel må ha et navn og brukes til å lagre en verdi. En variabel har derfor både et navn og en verdi. Det svaret du gir på funksjonen input blir da lagret i variabelen. Du kan kalle variabelen for navn.

   Hver instruksjon i Python skal skrives på en ny, blank linje. Før du skriver neste instruksjon, må du derfor trykke Enter.

   Skriv variabelnavnet og et likhetstegn foran input-setningen du nettopp skrev:

```
   navn = input("Hva heter du?")
```

6. Til slutt i dette programmet skal du bruke print-funksjonen på nytt. Da kan vi få programmet til å skrive ut verdien på variabelen navn. Men du skal bruke print litt annerledes enn i deloppgave A. Når vi bruker anførselstegn, vil meldingen som står mellom anførselstegnene bli skrevet ut nøyaktig slik det står. For å få skrevet ut verdien til variabelen navn, kan vi ikke bruke anførselstegn:

```
   print(navn)
```

8. Lagre endringene (**Ctrl+S**), gå tilbake til Terminal (**Ctrl+Ø**), og kjør programmet på nytt

```
   python navn.py
```

9. Hva skjedde da du kjørte programmet?
10. Du skal nå endre litt på print-funksjonen du nettopp brukte. I tillegg til å skrive verdien på variabelen navn, skal programmet også skrive en liten melding. Husk at vi må bruke anførselstegn for å skrive ut en melding nøyaktig slik den står, men at vi må sløyfe anførselstegnene når vi skal skrive ut en variabel. For å skrive ut både en melding og en variabel, må du skrive følgende:

```
   print("Hei " + navn)
```

11. Legg merke til at det står et mellomrom etter ordet hei. Det er for at Hei og verdien til variabelen navn ikke skal står helt inntil hverandre. Det ser bedre ut.

12. Lagre endringene (**Ctrl+S**), gå tilbake til Terminal (**Ctrl+Ø**) og kjør programmet på nytt. Hva ble annerledes denne gang?

#### Løsningsforslag

<details>
<summary>Klikk for å utvide.</summary>

```
   navn = input("Hva heter du?")
   print("Hei " + navn)
```

</details>
</details>
&nbsp;  

### Deloppgave C

Her skal du fortsette å utvide programmet fra deloppgave A og B. Du skal kontrollere om den som kjører programmet faktisk skriver inn noe og ikke bare trykker Enter.

<details>
<summary>Klikk for å utvide.</summary>

1. Gå først tilbake til programmet ditt (**Ctrl+1**).
2. Du kan beholde de to kodelinjene fra forrige deloppgave. Men du trenger mer kode i tillegg:
3. Du skal nå kontrollere om det ble oppgitt et navn. Det kan vi gjøre ved å sjekke om variabelen navn har en verdi eller ikke. Du kan bruke en if-setning.
4. Programkoden som skal stå inne i if-setningen skal utføres bare hvis if-setningen (det vil si betingelsen) er oppfylt. Hvis betingelsen er oppfylt, har den verdien True (sann). Hvis ikke, har den verdien False (usann). Du kan skrive det slik:

```
   if navn:
```

5. Inne i if-setningen må du skrive det som skal skje hvis betingelsen er oppfylt, altså hvis variabelen navn har en verdi. Bruk den samme print-kommandoen som du brukte tidligere.

6. Men hva hvis den som kjørere programmet ikke oppgav noe navn? Sammen med if-setningen brukes ofte en else-setning. Hvis if-setningen ikke blir oppfylt, vil programkoden i else-setningen utføres i stedet. I else-setningen kan du skrive en melding som gir beskjed om at det ikke ble oppgitt noe navn.
8. Lagre endringene (**Ctrl+S**), gå tilbake til Terminal (**Ctrl+Ø**).
9. Når du kjører programmet, kan du oppgi et navn på spørsmålet om hva du heter. Hva skjer da?
10. Kjør programmet på nytt. Denne gangen kan du la være å oppgi navn, trykk bare Enter i stedet. Hva skjer denne ang?

#### Løsningsforslag

<details>
<summary>Klikk for å utvide.</summary>

```
navn = input("Hva heter du?")
if navn:
       print("Hei " + navn)
else:
       print("Du oppgav ikke et navn!")
```

</details>
</details>
</details>
&nbsp;  

## Oppgave 2: Tekst-til-tale

Tekst-til-tale (eller talesyntese) kan brukes til å få datamaskinen din til å snakke. Oppgavene bruker tekst-til-tale-modulen **pyttsx3**.

<details>
<summary>Klikk for å utvide.</summary>

Utstyr: Visual Studio Code, høyttalere.

### Deloppgave A
   
I denne oppgaven skal du lage et lite program som leser opp en kort melding med tekst-til-tale.

<details>
<summary>Klikk for å utvide.</summary>

1. Før du kan bruke tekst-til-tale i Python, må du sørge for at det er installert. Gå til Terminal (**Ctrl+Ø**) og skriv:

```
    pip install pyttsx3
```

2. Nå som tekst-til-tale er installert, kan du gå i gang med å bruke det. Opprett en ny fil (**Ctrl+N**).
3. Lagre filen (**Ctrl+S**). Gi filen et navn (for eksempel hello.py).
4. Øverst i programmet ditt må du gi beskjed om at du skal bruke tekst-til-tale. Det gjør du slik:

```
    import pyttsx3
```

5. Lag en blank linje etter import-setningen. Så skal du skrive en instruksjon som betyr at du lager en talesyntese som du kaller engine. I fortsettelsen kan du bruke engine-navnet når du skal skrive flere instruksjoner:

```
    engine = pyttsx3.init()
```

6. Det neste som skal skje, er at du må bestemme hva talesyntesen skal si. Her skal du bruke engelsk. La oss for eksempel si at du skal bruke meldingen "Hello, world. How are you?". I programmet ditt må du da skrive:

```
    engine.say("Hello, world. How are you?")
```

7. I den siste setningen skal du bruke en instruksjon som starter opplesing av meldingen. Det gjør du slik:

```
    engine.runAndWait()
```

8. Lagre filen (**Ctrl+S**).
9. Gå til Terminal i Visual Studio Code (**Ctrl+Ø**).
10. Pass på så du har hodetelefoner eller høyttalere koblet til datamaskinen din.
11. Skriv kommandoen for å kjøre programmet ditt. Hvis programmet heter hello.py må du skrive:

```
    python hello.py
```

12. Ble det riktig?
13. Gå tilbake til programmet ditt med **Ctrl+1**.
14. Gjør en endring i programmet ditt slik at det leser opp en annen melding. Hva må du gjøre for å få til det?
15. Lagre endringene du gjorde (**Ctrl+S**) og gå tilbake til Terminal (**Ctrl+Ø**). Kjør programmet på nytt.

#### Løsningsforslag

   <details>
<summary>Klikk for å utvide.</summary>
      
```
import pyttsx3

engine = pyttsx3.init()
engine.say("Hello, world. How are you?")
engine.runAndWait()
```

</details>
   </details>
   &nbsp;  

### Deloppgave B

Nå skal du utvide programmet ditt fra deloppgave A ved å bruke en annen hastighet på stemmen.

<details>
<summary>Klikk for å utvide.</summary>

Det kan være morsomt å endre hastighet på stemmen som leser. Standard hastighet er 200 ord i minuttet. I forrige deloppgave tok du ikke med noe om hastighet og da brukes standardhastigheten automatisk. Men hva skjer hvis du endrer på det tallet?

1. Gå først tilbake til programmet ditt (**Ctrl+1**).
2. Finn tilbake til instruksjonen i programmet som ser slik ut: engine = pyttsx3.init().
3. Legg til en ny blank linje etter denne linja slik at du har plass til å skrive en ny instruksjon. Nå kan du bruke noe som heter setProperty. Den kan brukes for å endre forskjellige egenskaper ved talesyntesen, blant annet hastigheten. Skriv følgende instruksjon. Bytt ut `<hastighet>` med et tall. Tall større enn 200 betyr raskere, tall under 200 betyr langsommere:

```
    engine.setProperty('rate', <hastighet>)
```

4. Når vi skriver 'rate' så betyr det at det er hastigheten vi vil gjøre noe med. Og etter kommaet sier vi hvilken verdi hastigheten skal ha.
5. Lagre endringene (**Ctrl+S**), gå tilbake til Terminal (**Ctrl+Ø**), og kjør programmet på nytt:

```
    python hello.py
```

6. Hva skjedde da du kjørte programmet?
7. Prøv gjerne andre verdier på hastigheten og hør hvordan det påvirker talesyntesen.

#### Løsningsforslag

   <details>
<summary>Klikk for å utvide.</summary>
      
```
import pyttsx3

engine = pyttsx3.init()
engine.setProperty('rate', 400)
engine.say("Hello, world. How are you?")
engine.runAndWait()
```

   </details>
   </details>
   &nbsp;  
      
### Deloppgave C

I denne deloppgaven skal du velge en annen stemme til opplesingen.

<details>
<summary>Klikk for å utvide.</summary>

I forrige deloppgave endret du hastighet på talesyntesen. Det kan være morsomt å endre stemmen også. Hvor mange stemmer som finnes, kan variere fra datamaskin til datamaskin. Men ofte finnes det i hvert fall 2-3 stemmer.

1. Gå først tilbake til programmet ditt (**Ctrl+1**).
2. Finn tilbake til instruksjonen i programmet som ser slik ut: engine = pyttsx3.init().
3. Legg til en ny blank linje etter denne linja slik at du har plass til å skrive en ny instruksjon. Du skal fortsette å bruke setProperty, men nå er det en annen egenskap ved talesyntesen du skal endre, nemlig stemmen. Skriv følgende instruksjon:

```
    engine.setProperty('voice', voices[1].id)
```

4. Tenk deg at vi har en liste med stemmer vi kan velge fra. I programmering starter vi ofte på 0. Så når vi skriver 1, så betyr det altså den andre stemmen i lista.
5. Lagre endringene (**Ctrl+S**), gå tilbake til Terminal (**Ctrl+Ø**), og kjør programmet på nytt:

```
    python hello.py
```

6. Hva skjedde?
7. I de to første deloppgavene skrev du ikke noe om hvilken stemme programmet skulle bruke. Likevel brukte programmet ditt en stemme. Hvorfor det? Jo, hvis man ikke oppgir noen stemme, velges den stemmen som er standard. Og standard stemme er nummer 0. Når vi ikke skriver noe, er det altså stemme nummer 0 som blir brukt.
8. Prøv om det finnes flere stemmer på maskinen din som kan brukes. Gå først tilbake til programmet ditt (**Ctrl+1**). Finn tilbake til instruksjonen som du la til sist og velg stemme 2 i stedet for 1:

```
    engine.setProperty('voice', voices[2].id)
```
   
9. Hva skjedde denne gang? Hvis du ikke hørte noe, betyr det sannsynligvis at programmet ikke fant flere stemmer på maskinen. Du vil da få en feilmelding.

#### Løsningsforslag
   
<details>
<summary>Klikk for å utvide.</summary>
   
```
import pyttsx3

engine = pyttsx3.init()
engine.setProperty('voice', voices[2].id)
engine.setProperty('rate', 200)
engine.say("Hello, world. How are you?")
engine.runAndWait()
```
</details>
</details>
</details>
&nbsp;  

## Oppgave 3: Lyder med Winsound

Her er noen oppgaver som du kan bruke for å lage lyd på datamaskinen din. Her brukes **variable**, **lister**, **løkker (while og for)** og **iterasjon**, samt modulen **winsound**.

<details>
<summary>Klikk for å utvide.</summary>

Utstyr: Visual Studio Code, høyttalere.

### Deloppgave A

I denne deloppgaven skal du lage et lite program som bruker Winsound til å lage en pipelyd.

<details>
<summary>Klikk for å utvide.</summary>

1. Opprett en ny fil (**Ctrl+N**).
2. Lagre filen (**Ctrl+S**). Gi filen et navn (for eksempel pipelyd.py).
3. Øverst i programmet må du gi beskjed om at du skal bruke Winsound. Det gjør du slik:

```
    import winsound
```
4. Lag en blank linje etter import-setningen. Det første du skal bestemme er hvilken frekvens pipelyden skal ha og hvor lenge den skal vare. Til det skal du bruke to variabler. Den ene variabelen skal hete freq (frekvens i Hz) og den andre dur (varighet i millisekunder). 
5. Når du oppretter en variabel gir du den samtidig en verdi. Vi sier at vi tilordner en verdi. Først kommer navnet på variabelen, deretter et likhetstegn og til slutt verdien vi gir den. Opprett de to variablene nå.
6. Nå som du har bestemt frekvens og varighet på pipelyden, kan du bruke kommandoen som sender pipelyden til høyttaleren på datamaskinen din:

```
    winsound.Beep(freq, dur)
```

7. Hvilken tone har forresten frekvens på 440 Hz?

#### Løsningsforslag

<details>
<summary>Klikk for å utvide.</summary>

```
import winsound

freq = 440
dur = 1000
winsound.Beep(freq, dur)
```

</details>
</details>
&nbsp;  

### Deloppgave B

I denne deloppgaven skal du utvide programmet fra deloppgave B. Du skal bruke de samme variablene, men nå skal du bruke en løkke som spiller flere pipelyder etter hverandre. I tillegg skal frekvensen økes med 200 Hz for hver pipelyd.

<details>
<summary>Klikk for å utvide.</summary>

1. Fortsett med fila du laget i forrige deloppgave og behold all programkoden.
2. Nå skal du bruke en while-løkke. I en while-løkke bruker vi en betingelse. Så lenge betingelsen er oppfylt, vil koden i løkka gjentas. Når betingelsen ikke lenger oppfylles, vil programmet hoppe ut av løkka og gå videre.
3. I while-løkka skal du spille av en pipelyd slik du gjorde i forrige deloppgave. Men i tillegg skal du øke verdien av variabelen freq med 200 Hz. Betingelsen i løkka er at freq har verdi lavere enn 3000 Hz. Så lenge freq er lavere enn 3000, vil løkka gjentas. Men så snart freq blir høyere, hopper programmet ut av løkka.
4. Når du skriver while, trenger du et uttrykk som sjekker om freq er lavere enn 3000 Hz. Plasser while-løkka etter der du opprettet de to variablene:

```
    while freq < 3000:
```

5. Nå trenger du koden som skal stå inne i while-løkka. Bruk først kommandoen for å sende pipelyden til høyttalerne, altså samme kommando som i deloppgave A. Da du opprettet variablen freq gav du den verdien 440. Det blir frekvensen på den første pipelyden.
6. Men du skal spille flere pipelyder etter hverandre. Og for hver lyd skal frekvensen økes med 200 Hz.
7. Det går an å tenke seg dette slik: ny verdi av freq = nåværende verdi + 200. Skrevet i Python blir det slik:

```
    freq = freq + 200
```
8. I Python går det også an å skrive dette på en veldig kompakt måte. Velg selv hvilken du vil bruke:

```
    freq+= 200
```

9. Det er alt du trenger i løkka. Lagre filen (**Ctrl+S**) og kjør programmet.

#### Løsningsforslag

<details>
<summary>Klikk for å utvide.</summary>

```
import winsound
    
freq = 440
dur = 100
while freq < 3000:
    winsound.Beep(freq, dur)    
    freq+= 200
```

</details>
</details>
&nbsp;  

### Deloppgave C

Du kan også bruke Winsound til å spille av systemlyder. Systemlyder er korte snutter som spilles av når du gjør bestemte ting i Windows, for eksempel når du kobler til en USB-enhet.

<details>
<summary>Klikk for å utvide.</summary>

Det finnes mange systemlyder i Windows, men det er ikke sikkert at alle har fått tilordnet en lyd. Og flere systemlyder kan bruke samme lyd, dvs. en standardlyd. Dette varierer. Her er noen systemlyder du kan prøve: DeviceConnect, DeviceDisconnect, LowBatteryAlarm, Notification.Mail, Notification.SMS, SystemExit, WindowsLogoff, WindowsLogon.

1. Opprett en ny fil og start med å importere winsound.
2. Lagre fila (**Ctrl+S**) og gi den et passende navn (for eksempel systemlyd.py).
3. For å spille systemlyder, må du bruke PlaySound. Med Playsound blir instruksjonene litt mer kompliserte. Du må skrive winsound etterfulgt av punktum og så PlaySound: winsound.PlaySound().
4. Inne i parentesen må du så oppgi den systemlyden du vil spille av. Du må først skrive navnet på systemlyden og deretter komma etterfulgt av winsound.SND_ALIAS. Velg en av systemlydene, for eksempel DeviceConnect, over og skrive følgende uttrykk:

```
    winsound.PlaySound("DeviceConnect", winsound.SND_ALIAS)
```

5. Lagre filen (**Ctrl+S**) og kjør programmet.
6. Ble det riktig. Husk at det ikke er sikkert alle lydene du valgte har tilordnet noen lyd. Da vil du ikke høre noe.
7. Prøv en annen systemlyd. Lagre og kjør programmet på nytt.


#### Løsningsforslag

<details>
<summary>Klikk for å utvide.</summary>

```
import winsound

winsound.PlaySound("DeviceConnect", winsound.SND_ALIAS)
```

</details>
</details>
&nbsp;  

### Deloppgave D

I denne deloppgaven skal du videreutvikle programmet ditt fra forrige deloppgave. Det går an å legge flere lyder i en liste og så spille av hver lyd i lista ved hjelp av en løkke.

<details>
<summary>Klikk for å utvide.</summary>

I oppgaven kan du velge mellom de samme systemlydene som i forrige oppgave: DeviceConnect, DeviceDisconnect, LowBatteryAlarm, Notification.Mail, Notification.SMS, SystemExit, WindowsLogoff, WindowsLogon.

1. Gå tilbake til programmet ditt (**Ctrl+1**).
2. Det første du skal gjøre er å lage en liste med noen systemlyder. En liste i Python er en liste med verdier som er adskilt med komma, for eksempel dagene fra mandag til fredag:

```
    ukedager = ["mandag", "tirsdag", "onsdag", "torsdag", "fredag"]
```

3. Kall lista med systemlydene for lyder. Plukk ut noen av lydene i innledningen av oppgaven og skriv ferdig lista i programmet ditt. Skriv instruksjonen for lista etter import-setningen.
4. Du trenger også en variabel for å holde orden på hvor mange lyder lista inneholder. Du kan bruke metoden len(lyder) til dette. Den teller antall elementer i lista lyder og verdien blir tilordnet variabelen antall:

```
    antall = len(lyder)
```

5. Vi ønsker å bruke en løkke som går gjennom lista og spiller av hver enkelt lyd. Du kan bruke en for-løkke til dette. For-løkker skille seg fra while-løkker ved at løkka gjentas et bestemt antall ganger. I dette tilfellet vil vi at den skal gå gjennom lista like mange ganger som det er lyder i lista. Du kan skrive det slik:

```
    for i in range(antall):
```

6. i er bare en hjelpevariabel og variabelen antall har du allerede beregnet. Denne løkka vil gjentas antall ganger.
7. Til slutt må du skrive det som skal ligge inne i for-løkka. Det er det samme som du brukte i forrige deloppgave, bortsett fra at du ikke skal skrive navnet på lydene direkte. I stedet kan du henvise til lista med lyder. Bruk følgende uttrykk:

```
    winsound.PlaySound(lyder[i], winsound.SND_ALIAS)
```

8. I instruksjonen over vil i endre verdi for hver gang løkka gjentas.
9. Lagre filen (**Ctrl+S**) og kjør programmet.
10. Ble det riktig. Husk at det ikke er sikkert alle lydene du valgte har tilordnet noen lyd. Da vil du ikke høre noe.
11. Hvis du vil, kan du bytte ut noen av lydene i lista og prøve på nytt.

#### Løsningsforslag

<details>
<summary>Klikk for å utvide.</summary>

```
import winsound

lyder = ["Notification.Mail", "DeviceDisconnect", "WindowsLogon"]
antall = len(lyder)

for i in range(antall):
    winsound.PlaySound(lyder[i], winsound.SND_ALIAS)
```

</details>
</details>
&nbsp; 
</details>

