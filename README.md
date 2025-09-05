# balderjs-template

## Run
`npm install`  
`npx balderjs`

## Att tänka på
  
<details>
<summary>Vanliga fel vid if-satser</summary>

**Använda = istället för ==**
```
if (x = 1) // Fel
    write("Ett")
```                    
Gör en tilldelning. Variabeln x blir 1. Hela uttrycket blir 1, vilket sedan tolkas som sant.

```
if (x == 1) // Rätt
    write("Ett")
```        
**Använda =< istället för <=**
```
if (x =< 0) // Fel
    write("Mindre än eller lika med noll")
```                    
Skriv tecknen i den ordning man säger dem; "mindre än" eller "lika med".

```
if (x <= 0) // Rätt
    write("Mindre än eller lika med noll")
```                    
**Inte använda else-if om flera alternativ**
```
if (x == 0)
    write("Noll")
if (x == 1) // Fel 
    write("Ett")
else
    write("Annat")
```                    
Om x har värdet 0 så kommer både "Noll" och "Annat" att skrivas ut!

```
if (x == 0)
    write("Noll")
else if (x == 1) // Rätt
    write("Ett")
else
    write("Annat")
```                
**Använda &&, eller ||, utan två villkor**
```
if (x == 0 || 1) // Fel
    write("Noll eller ett")
```                    
På båda sidor om || så måste det finnas ett villkor.

```
if (x == 0 || x == 1) // Rätt
    write("Noll eller ett")
```                    
Samma sak gäller för &&.

**Testa intervall utan &&**
```
if (0 <= x <= 10) // Fel
    write("I intervallet [0, 10]")
```                    
De två villkoren måste sättas ihop med &&.

```
if (0 <= x && x <= 10) // Rätt
    write("I intervallet [0, 10]")
```                 
**Använda indentering istället för satsblock**
```
if (x < 0)
    write("Negativt. Byt tecken")
    x = -x; // Fel
```
                    
Den sista satsen kommer alltid att utföras, även då x är positivt. Fixa till det genom att skapa ett satsblock.

```
if (x < 0) { // Rätt
    text("Negativt. Byt tecken");
    x = -x
}
```                 
**Fel ordning vid flera olikhetstester**
```
if (n < 1000)
    write("n mindre än 1000") // Fel
else if (n < 100)
    write("n mindre än 100")
else if (n < 10)
    write("n mindre än 10")
```                 
Den första satsen blir sann för alla värden mindre än tusen, de övriga testas aldrig. Ett n-värde på 42 skulle producera utskriften "n mindre än 1000" och inte, som avsett, "n mindre än 100".

```
if (n < 10)
    write("n mindre än 10") // Rätt
else if (n < 100)
    write("n mindre än 100")
else if (n < 1000)
    write("n mindre än 1000")
```
</details>

## Uppgifter
Du kan skriva följande deluppgifter i samma projekt. För att köra testerna kan du sedan kommentera ut kod som inte hör till den deluppgift som du arbetar med. Du kan kommentera med hjälp av:

/*  
Kod som du vill  
kommentera bort  
*/

För den som vill ha mer utmaning kan man göra varje deluppgift som en funktion, sen får användaren välja vilken deluppgift programmet ska köra (men då fungerar inte testerna).

Du kommer behöva använda read- och write-funktionerna för de här uppgifterna. Det skiljer sig från tidigare uppgifter då du ritat på canvas.


### Deluppgift 1
Gör ett program som frågar efter din ålder och skriver ut om du är myndig (minst 18 år) eller inte.

```
Ålder: 17
Omyndig
```

[Test 1](http://balder.skelamp.se/kurser/prog1/test/?i=17&o=Omyndig)
[Test 2](http://balder.skelamp.se/kurser/prog1/test/?i=18&o=Myndig)
[Test 3](http://balder.skelamp.se/kurser/prog1/test/?i=99&o=Myndig)

### Deluppgift 2
Gör ett program som frågar hur lång du är. Om svaret är under 200 ska programmet säga "Hej du korte!" annars "Hej du långe!".

```
Hur lång är du (i cm)? 202
Hej du långe!
```

[Test 1](http://balder.skelamp.se/kurser/prog1/test/?i=202&o=Hej%20du%20l%C3%A5nge!)
[Test 2](http://balder.skelamp.se/kurser/prog1/test/?i=199&o=Hej%20du%20korte!)

### Deluppgift 3
Gör ett program som läser in ett tal och presenterar en av utskrifterna "Talet är negativt.", "Talet är positivt." eller "Talet är noll.".

```
Ett tal: -32
Talet är negativt.
```

[Test 1](http://balder.skelamp.se/kurser/prog1/test/?i=-32&o=Talet%20%C3%A4r%20negativt.)
[Test 2](http://balder.skelamp.se/kurser/prog1/test/?i=1&o=Talet%20%C3%A4r%20positivt.)
[Test 3](http://balder.skelamp.se/kurser/prog1/test/?i=0&o=Talet%20%C3%A4r%20noll.)

### Deluppgift 4
In med värden till variablerna x och y. Ut med något av meddelandena "x = y", "x < y" eller "x > y".

```
x = 5
y = 7
x < y
```

[Test 1](http://balder.skelamp.se/kurser/prog1/test/?i=5%0A7&o=x%20%3C%20y)
[Test 2](http://balder.skelamp.se/kurser/prog1/test/?i=1%0A-1&o=x%20%3E%20y)
[Test 3](http://balder.skelamp.se/kurser/prog1/test/?i=0%0A0&o=x%20%3D%20y)

### Deluppgift 5
Gör ett litet beräkningsprogram enligt nedan.

```
Tal 1: 34
Tal 2: 75
Operator (+, -, *, /): +
Summa: 109
```
[Test 1](http://balder.skelamp.se/kurser/prog1/test/?i=34%0A75%0A%2B&o=Summa%3A%20109)
[Test 2](http://balder.skelamp.se/kurser/prog1/test/?i=10%0A7%0A-&o=Differens%3A%203)
[Test 3](http://balder.skelamp.se/kurser/prog1/test/?i=9%0A9%0A*&o=Produkt%3A%2081)
[Test 4](http://balder.skelamp.se/kurser/prog1/test/?i=1%0A4%0A%2F&o=Kvot%3A%200.25)

### Deluppgift 6
Skriv ett program som givet ett spelkorts valör (1-13) kan skriva vad spelkortet är. Låt 1 motsvara ess, 11 knekt, 12 dam och 13 kung.

```
Valör (1-13): 7
En 7:a
```

[Test 1](http://balder.skelamp.se/kurser/prog1/test/?i=7&o=En%207%3Aa)
[Test 2](http://balder.skelamp.se/kurser/prog1/test/?i=1&o=Ett%20ess)
[Test 3](http://balder.skelamp.se/kurser/prog1/test/?i=12&o=En%20dam)

### Deluppgift 7
Läs in ett månadsnummer (1-12) och skriv ut namnet på månaden.

```
Månadsnummer: 10
Oktober
```

[Test 1](http://balder.skelamp.se/kurser/prog1/test/?i=10&o=Oktober)
[Test 2](http://balder.skelamp.se/kurser/prog1/test/?i=1&o=Januari)

### Deluppgift 8
Läs in ett månadsnummer och skriv ut vilken årstid det motsvarar. Låt månad 12, 1, 2 motsvara vinter, 3-5 vår, 6-8 sommar och 9-11 höst.

```
Månadsnummer: 10
Höst
```

[Test 1](http://balder.skelamp.se/kurser/prog1/test/?i=10&o=H%C3%B6st)
[Test 2](http://balder.skelamp.se/kurser/prog1/test/?i=1&o=Vinter)

### Deluppgift 9
Skriv ett program där du skriver in två heltal och sedan försöker beräkna deras produkt. Programmet rättar dig om räknat fel.

```
Tal 1: 11
Tal 2: 12
Produkt: 130
Fel. Rätt svar: 132
```

[Test 1](http://balder.skelamp.se/kurser/prog1/test/?i=11%0A12%0A130&o=Fel.%20R%C3%A4tt%20svar%3A%20132)
[Test 2](http://balder.skelamp.se/kurser/prog1/test/?i=13%0A13%0A169&o=R%C3%A4tt!)

### Deluppgift 10
In med två heltal och ut med lite info om talen på följande sätt:

```
Tal 1: 4
Tal 2: 7
Summa: 11
Medel: 5.5
Minsta: 4
Största: 7
```

[Test 1](http://balder.skelamp.se/kurser/prog1/test/?i=4%0A7&o=Summa%3A%2011%0AMedel%3A%205.5%0AMinsta%3A%204%0ASt%C3%B6rsta%3A%207)
[Test 2](http://balder.skelamp.se/kurser/prog1/test/?i=9%0A7&o=Summa%3A%2016%0AMedel%3A%208%0AMinsta%3A%207%0ASt%C3%B6rsta%3A%209)

### Deluppgift 11
Gör föregående uppgift med tre tal istället.

[Test 1](http://balder.skelamp.se/kurser/prog1/test/?i=5%0A10%0A7&o=Summa%3A%2022%0AMedel%3A%207.3%0AMinsta%3A%205%0ASt%C3%B6rsta%3A%2010)

### Deluppgift 12
Detta program ska kunna avgöra om ett inmatat tecken är en liten bokstav, stor bokstav eller annat tecken. Det räcker om det fungerar för tecken i det engelska alfabetet (A-Z).

```
Tecken: B
Stor bokstav
```

[Test 1](http://balder.skelamp.se/kurser/prog1/test/?i=B&o=Stor%20bokstav)
[Test 2](http://balder.skelamp.se/kurser/prog1/test/?i=p&o=Liten%20bokstav)
[Test 3](http://balder.skelamp.se/kurser/prog1/test/?i=!&o=Annat%20tecken)

### Deluppgift 13
Detta program ska kunna avgöra om ett inmatat tecken är en liten bokstav, stor bokstav eller annat tecken. Det räcker om det fungerar för tecken i det engelska alfabetet (A-Z).

```
Mata in ett tal mellan -999 och 999: 32
Två siffror
Positivt
```

[Test 1](http://balder.skelamp.se/kurser/prog1/test/?i=32&o=Tv%C3%A5%20siffror%0APositivt)
[Test 2](http://balder.skelamp.se/kurser/prog1/test/?i=-100&o=Tre%20siffror%0ANegativt)
[Test 3](http://balder.skelamp.se/kurser/prog1/test/?i=0&o=En%20siffra%0ANoll)

### Deluppgift 14
Om tre tal ska kunna vara sidor i en triangel så måste samtliga tal vara större än noll och inget tal större än de andra två tillsammans. Skriv ett program som frågar efter längden på tre sidor och som kollar om en triangel kan bildas med de angivna värdena.

```
Sida 1: 5
Sida 2: 10
Sida 3: 4
Triangel? Nej!
```

[Test 1](http://balder.skelamp.se/kurser/prog1/test/?i=5%0A10%0A4&o=Triangel%3F%20Nej!)
[Test 2](http://balder.skelamp.se/kurser/prog1/test/?i=5%0A6%0A7&o=Triangel%3F%20Ja!)