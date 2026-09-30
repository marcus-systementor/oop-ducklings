# Hjälp – en ledtråd i taget

Läs först den första ledtråden för ditt steg. Prova en liten ändring och kör igen innan du läser nästa. Det finns ingen färdig lösning här.

## Körning

1. Stå i repositoryts rot och kör `python student/ducklings.py`. Prova `py` eller `python3` om datorn använder det kommandot.
2. Spara filen före körning. Vid ett fel: läs exception på sista raden och hitta fil och radnummer ovanför. Dela kommando, checkpoint, felmeddelande och din hypotes när du ber om hjälp.

## Steg 2–3: class och __init__

1. En class-definition beskriver en typ. Ett anrop med parenteser skapar en instance. Kontrollera vilken av dessa två saker du har i din variabel.
2. Indrag visar vad som hör till class och vad som körs efter dess definition. En method ligger inne i class; skapandet av ankungen ligger utanför.
3. Om ett namn-argument inte accepteras: kontrollera stavningen på `__init__`, dess dubbla understreck och dess parameters. Om `name` inte finns på object: fundera på var det sparas och skillnaden mellan `name` och `self.name`.

## Steg 4: method och return

1. Ska metoden skriva ut texten själv eller ge den tillbaka? Läs målet igen och skilj på `print()` och `return`.
2. Om utskriften är `None`, kontrollera vad metoden returnerar. Om du ser en beskrivning av en method i stället för dess text, kontrollera att du faktiskt anropar den.
3. Om du får ett fel om antal arguments, kontrollera metodens första parameter och hur anropet skrivs på object.

## Steg 5: eget state

1. Tre namn i en list innebär inte automatiskt tre objects. Hur många gånger anropas `Duckling(...)` när du bygger flocken?
2. Förutsäg vad som händer med de andra ankornas namn när bara `first.name` ändras. Kontrollera sedan om listan verkligen innehåller tre separata instances.

## Steg 6: ögon och random

1. Få de fasta ögonvalen att fungera först. Då ser du om problemet ligger i textbilden eller i slumpvalet.
2. Om samma object ändrar utseende när det skrivs ut igen, kontrollera **när** `random.choice()` körs. `__init__` ska spara valet; `describe()` ska läsa det.
3. Samma ögon på två olika ankungar är ett möjligt slumpresultat. Använd kontrollen med olika namn och den tillfälliga ändringen av bara ett attribute för att undersöka självständighet.

## Frivillig scrollning

1. Börja med några få varv och ingen paus. Lägg till `time.sleep()` först när raderna ser rätt ut.
2. Kör i terminalen. Ctrl+C avbryter en lång körning; en ändlig `for`-loop avslutas också självt.

Om en `commit` inte innehåller din ändring, kontrollera att filen är sparad och att Git ser den som ändrad. Be om hjälp med åtkomst om `push` från ditt eget repository inte fungerar. Återgå gärna till [README.md](README.md) och anteckna din fråga i [REFLECTION.md](REFLECTION.md).
