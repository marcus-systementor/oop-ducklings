# Ducklings – en liten flock med egna attributes

Du bygger ett litet program där varje ankunge är ett eget `object`. Projektet är inspirerat av Project 22, *Ducklings*, i Al Sweigarts *The Big Book of Small Python Projects*. Vår övning använder en enklare, egen textbild och originalinstruktioner.

Du övar skillnaden mellan `class` och `instance`, `__init__`, `self`, attributes och methods. Sedan använder du en list, en loop och `random.choice()`. Du behöver kunna grunderna i variabler, strängar, `print()`, functions, `return`, lists och loops. Endast Pythons standard library behövs.

Arbeta i ordning. Ett litet fungerande steg är bättre än flera halvfärdiga. Det går bra att stanna efter vilket steg som helst och fortsätta senare. Planera gärna ett par timmar för steg 1–6 med pauser och tid att läsa [HJALP.md](HJALP.md). Steg 7 är frivilligt. Ingen animation krävs för att grundlabben ska vara klar.

## Kom igång och spara arbetet

Om materialet delas som en GitHub-template: välj **Use this template**, skapa ett eget **Private** repository och klona **ditt eget** repository. Öppna repositoryts rot i VS Code. Där finns README och mappen `student/`.

Kör från repositoryts rot:

```text
python student/ducklings.py
```

På Windows kan kommandot vara `py student/ducklings.py`; på vissa datorer `python3 student/ducklings.py`. Använd samma variant vid varje steg. Du behöver inte installera några paket. Startfilen innehåller bara välkomsttext och små TODO-kommentarer.

Efter varje färdigt steg: spara filen, kör kontrollen och gör en `commit` i ditt eget repository med det föreslagna engelska meddelandet. Om Git ännu inte är ordnat kan du fortsätta skriva kod och be om hjälp senare. [REFLECTION.md](REFLECTION.md) fyller du i med egna ord medan du arbetar.

## Steg 1 – kör och läs startfilen

**Mål:** Du vet vad programmet gör just nu och hur du kör det.

**Fil och uppgift:** Öppna `student/ducklings.py`. Läs raderna med `print()` och TODO-kommentarerna. Inga duckling-objects finns ännu. Skriv en kort anteckning om startutskriften i fråga 1 i `REFLECTION.md`.

**Kör:** `python student/ducklings.py` från repositoryts rot.

**Checkpoint:** Två rader ska visas och programmet ska sedan avslutas:

```text
Ducklings
One small step at a time.
```

**Commit:** `Record the starter observation`

## Steg 2 – en class och ett object

**Mål:** Du skapar ett object från en egen `class`.

**Fil och uppgift:** Redigera `student/ducklings.py`. Lägg till en `class Duckling:` efter välkomstutskriften. En class beskriver vilken typ av object du vill skapa. En class måste ha ett indraget innehåll; använd tills vidare `pass`, som betyder att inget ska göras där ännu. Efter class-definitionen, utan indrag, skapa `duckling = Duckling()`. Anropet med parenteser skapar en ny instance av Duckling. Här betyder `object` och `instance` samma konkreta ankunge.

Använd tillfälligt `print(type(duckling))` för att se vilken typ ditt object har. `type()` visar typen på ett värde.

**Kör:** `python student/ducklings.py`.

**Checkpoint:** Efter de två välkomstraderna ska typens utskrift innehålla `Duckling`, normalt `<class '__main__.Duckling'>`. Programmet ska avslutas utan fel. Att skriva `Duckling` utan parenteser skulle referera till själva class, inte skapa ankungen.

**Commit:** `Create the first Duckling object`

## Steg 3 – __init__ och ett eget namn

**Mål:** Din instance får ett `name` när den skapas.

**Fil och uppgift:** Redigera `student/ducklings.py`. Ersätt `pass` med en indragen `__init__(self, name)`-method. Metoder skrivs med `def` inne i en class. Spara namnet som ett instance-attribute med `self.name = name` inne i metoden. Byt sedan object-anropet till `Duckling("Pip")`. Ersätt den tillfälliga typ-utskriften med en utskrift av `duckling.name`.

När du skriver `Duckling("Pip")` skapas en ny instance och Python kör dess `__init__` för att initiera den. Det sker vid skapandet, inte varje gång du senare skriver ut ankungen. `self` refererar till just den instance som initieras; `name` är värdet du skickade in. Du skickar **inte** själv in `self` i anropet. `self.name` sparas på object, så att andra methods kan läsa det senare.

**Kör:** `python student/ducklings.py`.

**Checkpoint:** Namnet som skrivs efter välkomsttexten är `Pip`. Ändra tillfälligt argumentet till `"Dot"`: utskriften ska bli `Dot`. Sätt tillbaka `"Pip"` inför nästa steg.

**Commit:** `Initialize each duckling with a name`

## Steg 4 – en method som returnerar text

**Mål:** Ankungen kan ge tillbaka en enkel textrepresentation.

**Fil och uppgift:** Redigera `student/ducklings.py`. Lägg till `describe(self)` som en ny method inne i `Duckling`, på samma indragsnivå som `__init__`. Den ska använda `self.name` och `return` för att ge tillbaka text av formen `Pip: quack!`. Du kan sätta ihop strängar med `+`. Låt metoden ge tillbaka texten; låt `print()` utanför class visa den. Ersätt den tidigare namn-utskriften med `print(duckling.describe())`.

I `duckling.describe()` blir `self` automatiskt ankungen som namnet `duckling` refererar till. `return` skickar tillbaka text till anroparen; det skriver inte ut den.

**Kör:** `python student/ducklings.py`.

**Checkpoint:** Efter välkomsttexten ska du få `Pip: quack!`. Om du ändrar namnet till `Dot` ska samma method ge `Dot: quack!`. Sätt tillbaka `Pip`.

**Commit:** `Return a duckling description`

## Steg 5 – flera självständiga instances

**Mål:** En list håller flera objects med egna namn.

**Fil och uppgift:** Redigera `student/ducklings.py`. Ersätt skapandet av den ensamma ankungen och dess utskrift med tre separata anrop till `Duckling`: spara dem som `first`, `second` och `third`, med namnen `Pip`, `Dot` och `Moss`. Lägg dem i `ducklings = [first, second, third]`. Använd en `for`-loop som skriver varje objects `describe()`-resultat. Du behöver inte ändra class för att skapa fler instances.

Kontrollera sedan eget state: lägg tillfälligt till `first.name = "Sunny"` före loopen och förutsäg alla tre raderna innan du kör. Ta bort den tillfälliga ändringen när kontrollen är klar.

**Kör:** `python student/ducklings.py` efter varje ändring.

**Checkpoint:** Först får du `Pip: quack!`, `Dot: quack!`, `Moss: quack!` i listans ordning. Med ändringen blir bara första raden `Sunny: quack!`; de andra två är oförändrade. Efter att du tagit bort ändringen blir första raden åter `Pip: quack!` vid nästa körning.

**Commit:** `Display three independent ducklings`

## Steg 6 – utseende först med fasta val, sedan random

**Mål:** Varje instance får ett eget ögonutseende som håller sig stabilt.

**Fil och uppgift:** Redigera `student/ducklings.py` i två små delar:

1. Lägg till `self.eyes = "o"` i `__init__`. Ändra `describe()` så att den returnerar namn, en liten textbild och ljud: exempelvis `Pip: (o)> quack!`. Använd `self.eyes` i bilden. Prova sedan tillfälligt `second.eyes = "^"` före loopen, så att Dot får bilden `(^)>`. Kontrollera det innan du fortsätter.
2. Ta bort den tillfälliga ändringen av Dot. Lägg `import random` överst i filen. `random.choice()` väljer ett värde ur en list; ersätt det fasta ögonvärdet i `__init__` med ett val ur `["o", "^"]`. Gör valet **vid skapandet**, så att `describe()` bara läser ett redan sparat attribute.

**Kör:** `python student/ducklings.py` efter del 1 och efter del 2.

**Checkpoint:** Med fasta val får Pip och Moss `(o)>`, medan Dot får `(^)>`. Med random får varje ankunge något av dessa två utseenden. Flera kan råka få samma; det betyder inte att de är samma object. Prova tillfälligt att skriva `first.describe()` två gånger: namnet och ögonen ska vara lika båda gångerna i samma körning. Ta bort kontrollutskrifterna efteråt.

**Commit:** `Give ducklings a stable random appearance`

## Steg 7 – frivilligt: en enkel scrollande flock

**Mål:** Du provar en begränsad scrollande utskrift med dina befintliga objects.

**Fil och uppgift:** Grundlabben är färdig efter steg 6. Om du vill fortsätta, spara först den versionen med `commit`. Redigera sedan `student/ducklings.py` och lägg en separat demonstrations-loop sist i filen. Använd `for position in range(20)` för 20 varv med positionerna 0–19. Välj en ankunge ur din befintliga list med `random.choice(ducklings)`. För varje varv, skriv dess beskrivning med lite fler mellanslag framför än förra raden. Strängen `" " * position` ger `position` mellanslag; sätt ihop dem med beskrivningen.

Lägg `import time` överst. `time.sleep(0.3)` pausar körningen i 0,3 sekunder; använd en paus efter varje rad. Raderna växer nedåt i terminalen, utan att du behöver rensa skärmen eller flytta markören. Behåll en **ändlig** loop. Kör i terminalen och tryck **Ctrl+C** om du vill stoppa tidigare. Ett `KeyboardInterrupt` vid detta frivilliga test är normalt och behöver inte fångas.

**Kör:** `python student/ducklings.py`.

**Checkpoint:** Efter den vanliga flocken visas 20 nya rader med ökande indrag och programmet avslutas självt. Ctrl+C ska stoppa tidigare. Ankungen som väljs behåller sina attributes; scrollandet behöver inte ändra class eller `describe()`.

**Commit:** `Add a finite scrolling duckling display`

## Klart för idag

Grundversionen är klar när tre Duckling-instances har egna namn och ögon, deras text visas med en loop och samma object ger samma beskrivning i en körning. Svara i [REFLECTION.md](REFLECTION.md). Om ett steg är svårt, skriv vilket checkpoint-resultat du får och använd [HJALP.md](HJALP.md) innan du går vidare.
