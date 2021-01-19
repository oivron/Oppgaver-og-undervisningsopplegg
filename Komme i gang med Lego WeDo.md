# Komme i gang med Lego WeDo

Før du begynner på disse oppgavene, kan det lønne seg å prøve noen enkle Python-oppgaver først.

## Kjør en meter med roboten Milo
<details>
<summary>Klikk for å utvide.</summary>

Utstyr: WeDo 2.0 legobrikker, BLE112-dongle, Visual Studio Code.

### Deloppgave A: Bygg Milo

1.	Bygg roboten Milo med legobrikkene som følger med WeDo 2.0-settet. [Her finner du byggeinstruksjonene](https://education.lego.com/v3/assets/blt293eea581807678a/blt93919edff44b5450/5f88037fb8b59a77a945d172/45300_16_milo.pdf).
2.	Sett 2 AA-batterier inn i Smarthub-enheten.

### Deloppgave B: Programmer Milo

1.	Åpne Visual Studio Code.
2.	Opprett en ny fil (**Ctrl+N**).
3.	Lagre filen (**Ctrl+S**) som en python-fil (filnavn.py).
4.	Helt først i programmet ditt må du ha en setning som importerer Python-modulen for WeDo Smarthub. Smarthub er motoren som styrer alle bevegelser:

    ```
    from wedo2.smarthub import Smarthub
    ```
 
5.	Deretter må du importere time-modulen som gjør at du kan bestemme hvor lenge Milo skal kjøre:

    ```
    from time import sleep
    ```
 
6.	Lag en blank linje og skriv så en instruksjon som kreves for at du skal få kontakt med Smarthub:

    ```
    hub = Smarthub()
    ```

7.	Du trenger nå en instruksjon som setter i gang motoren og bestemmer hastigheten. Husk at farten kan variere fra 0 til 100 der 100 er maks hastighet. Velg halv fart, det vil si 50:

    ```
    hub.turn_motor(50)
    ```
 
8.	Etter at du har satt i gang motoren, må du bestemme hvor lenge den skal gå. Sleep kan brukes til å si hvor lang tid som skal gå før programmet går videre til neste instruksjon eller setning. Bytt ut millisekunder i koden under med et tall. Hvilken verdi må du bruke for at Milo skal kjøre én meter? Verdien skal altså oppgis i millisekunder. Hvor mye er det?

    ```
    sleep(<millisekunder>)
    ```
 
    Hvis Milo kjørte for langt eller for kort, kan du endre tallet slik at det passer bedre.

9.	Etter at programmet har ventet i det antall millisekunder du oppgav, går det videre til neste instruksjon som vil stoppe Milo:

    ```
    hub.motor_brake()
    ```
 
10.	Til slutt må du skrive en instruksjon som kobler fra Smarthub:

    ```
    hub.disconnect()
    ```
 
11.	Lagre alle endringer i programmet ditt med **Ctrl+S**.
12.	Sørg for at Bluetooth-donglen er tilkoblet.
13.	Trykk på knappen øverst på Smarthub.
14.	Overfør programmet med **Ctrl+F5**.
15.	Etter noen sekunder begynner Milo å kjøre.
</details>

## Bruke sonar
<details>
<summary>Klikk for å utvide.</summary>

Utstyr: WeDo 2.0 legobrikker, BLE112-dongle, Visual Studio Code.

I denne oppgaven skal du programmere Milo slik at den kjører rett fram helt til den møter en hindring. Da skal den stoppe av seg selv.

### Deloppgave A: Bygg om Milo

1.	Først skal du bygge om roboten Milo slik at den får en sonar eller avstandssensor. Fortsett med å bruke legobrikkene som følger med WeDo 2.0-settet. [Her finner du byggeinstruksjonene](https://education.lego.com/v3/assets/blt293eea581807678a/blt46478dce52b89471/5f88038df71916144453a4a3/45300_16a_milo_arm-1_modified_24102016_.pdf).

### Deloppgave B: Programmere Milo

1.	Åpne Visual Studio Code.
2.	Opprett en ny fil (**Ctrl+N**).
3.	Lagre filen (**Ctrl+S**) som en python-fil (filnavn.py).
4.	Først i programmet ditt må du ha de to importertsetningene:

    ```
    from wedo2.smarthub import Smarthub
    from time import sleep
    ```
 
5.	Så må du ha instruksjonen som lar deg få kontakt med Smarthub:

    ```
    hub = Smarthub()
    ```

6.	Nå skal du skrive noen instruksjoner som gjør at Milo kjører helt til den møter en hindring. Da skal den stoppe for å unngå kollisjon. Du må bruke en while-løkke som gjør at Milo hele tiden følger med på om det kommer noe i veien for den:

    ```
    while True:
    ```

7.	Inne i while-løkka må du sette betingelser for hva som skal skje. Avstandssensoren sender hele tiden informasjon om det den oppdager foran seg. Hvis den oppdager en hindring vil den sende et tall mindre enn 10. Hvis den ikke oppdager noen hindring, sender den tallet 10. Dette kan du bruke når du skal sette betingelser. Betingelser eller vilkår kan du lage med if og elif. If-setningen kan du bruke til å si hva som skal skje hvis det ikke er noen hindring:

    ```
    if hub.get_object_distance() == 10
    ```

8.	Hva skal skje dersom det ikke er noen hindringer foran roboten? Skriv en instruksjon for dette. På samme måte kan du bruke elif for å si hva som skal skje når det dukker opp en hindring:

    ```
    elif hub.get_object_distance() < 10
    ```

9.	Hvis det dukker opp en hindring, må roboten stoppe. Det kan du gjøre slik:

    ```
    motor_brake()
    ```

10.	Fullfør while-løkka med if og elif slik at det blir riktig. Husk innrykk i koden.
11.	Til slutt må du koble fra Smarthub:

    ```
    hub.disconnect()
    ```

12.	Lagre alle endringer i programmet ditt med **Ctrl+S**.
13.	Sørg for at Bluetooth-donglen er tilkoblet.
14.	Trykk på knappen øverst på Smarthub.
15.	Overfør programmet med **Ctrl+F5**.
16.	Etter noen sekunder begynner Milo å kjøre.
</details>