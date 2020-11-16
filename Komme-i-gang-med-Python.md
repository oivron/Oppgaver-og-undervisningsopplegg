## Komme i gang med programmering

Grunnleggende ppgaver i Python.

### Oppgave 1: Skriv navnet ditt (Python)
<details>
<summary>Klikk for å utvide.</summary>

Utstyr: Visual Studio Code.

#### Deloppgave A

I denne deloppgaven skal du lage et lite program som skriver en melding på skjermen. Meldingen skal være fornavnet ditt.

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

#### Deloppgave B

I denne deloppgaven skal du utvide programmet fra deloppgave A. Vi kan få programmet til å spørre etter navnet på den som skal kjøre programmet. Hun må da taste inn navnet sitt. Til slutt skal programmet skrive navnet på skjermen.

1. Gå først tilbake til programmet ditt (**Ctrl+1**).
2. Opprett en ny fil (**Ctrl+N**).
3. Lagre filen (**Ctrl+S**). Gi filen et navn (for eksempel hvaheterdu.py).
4. Først må vi bruke en funksjon som heter input. Input bruker vi litt på samme måte som print, det vil si at vi trenger parenteser etter input og anførselstegn inne i parentesene. Når programmet inneholder input, vil programmet stoppe opp og vente på svar fra deg. Du må da skrive inn et svar og trykke Enter:

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

7. Programmet ditt skal nå se slik ut:

```
navn = input("Hva heter du?")
print(navn)
```

8. Lagre endringene (**Ctrl+S**), gå tilbake til Terminal (**Ctrl+Ø**), og kjør programmet på nytt:

```
python hvaheterdu.py
```

9. Hva skjedde da du kjørte programmet?
10. Du skal nå endre litt på print-funksjonen du nettopp brukte. I tillegg til å skrive verdien på variabelen navn, skal programmet også skrive en liten melding. Husk at vi må bruke anførselstegn for å skrive ut en melding nøyaktig slik den står, men at vi må sløyfe anførselstegnene når vi skal skrive ut en variabel. For å skrive ut både en melding og en variabel, må du skrive følgende:

```
print("Hei " + navn)
```

11. Legg merke til at det står et mellomrom etter ordet hei. Det er for at Hei og verdien til variabelen navn ikke skal står helt inntil hverandre. Det ser bedre ut. Programmet ditt ser nå slik ut:

```
navn = input("Hva heter du?")
print("Hei " + navn)
```

12. Lagre endringene (**Ctrl+S**), gå tilbake til Terminal (**Ctrl+Ø**) og kjør programmet på nytt. Hva ble annerledes denne gang?
13. Ta en skjermdump av programvinduet til Visual Studio Code.
</details>

