# Week 6 — Casino de Gouden Driehoek: Rich-opmaak, random en datumverwerking

## Inleiding
Vorige week heb je spelersprofielen slimmer gemaakt met dictionaries en sets. Deze week maak je het casino mooier, betrouwbaarder en dynamischer. Je voegt Rich toe voor een nette terminalopmaak, je laat de spellen echte willekeur gebruiken met `random` en je verwerkt geboortedata voortaan netjes met een datumfunctie uit de standaardbibliotheek.

## Opdracht beschrijving
Breid het casino uit op drie punten:

### 1. Rich-opmaak
Gebruik het externe pakket **Rich** om de bestaande output van het casino mooier te maken. Denk aan:
- Het hoofdmenu
- De spellen
- Het accountoverzicht
- meldingen bij winst, verlies of fouten

Zorg dat alle algemene print-outs in een Panel geprint worden met de naam van het casino en het onderdeel als titel. Het gaat hier om prints zoals `Casino de Gouden Driehoek - saldo` of `Casino de Gouden Driehoek - hoofdmenu` (misschien gebruikt jouw implementatie andere benamingen) en de prints die daarop volgen. Het welkomstbericht zou er als volgt uit kunnen zien: 
```text
┌───────────────────────── Casino de Gouden Driehoek ─────────────────────────┐
│ Welkom, meneer Bond                                                         │
│                                                                             │
│ Startbudget: € 1000000.00                                                   │
│ Vaste kosten: € 16.50                                                       │
│ Saldo: € 999983.50                                                          │
│                                                                             │
│ Je hebt nog genoeg budget voor toegang tot het casino.                      │
└─────────────────────────────────────────────────────────────────────────────┘
```

Zorg dat alle opsommingen, zoals de menu opties of de roulette opties, in een Tabel geprint staan. Het hoofdmenu zou er als volgt uit kunnen zien: 
```text
┌─ Casino de Gouden Driehoek - hoofdmenu ─┐
│ ┌────────────────┬────────────────────┐ │
│ │ Optie          │ Actie              │ │
│ ├────────────────┼────────────────────┤ │
│ │ 1              │ Spellen            │ │
│ │ 2              │ Saldo              │ │
│ │ 3              │ Account            │ │
│ │ 0              │ Stop               │ │
│ └────────────────┴────────────────────┘ │
└─────────────────────────────────────────┘
```

Zorg dat alle spel resultaten getoond worden in een eigen Panel. Wees hier niet te streng in wat nou een "spel resultaat" is en wat niet, zorg vooral dat het er degelijk uit ziet.

Je mag zelf kiezen hoe ver de opmaak gaat, zolang de basisinformatie nog steeds duidelijk zichtbaar is. Je hoeft dus niet exact één layout te volgen, maar de belangrijke informatie moet wel gepolijst worden met Rich. Gebruik bijvoorbeeld ook in-text opmaak, zoals dikgedrukte woorden of gekleurde tekst. Bijvoorbeeld door groen te gebruiken om te printen dat de gebruiker gewonnen heeft en rood om te printen dat de gebruiker verloren heeft.

### 2. Random in de spellen
De bestaande spellen mogen nu echt willekeurig worden. In `blackjack.py` hebben we al random gebruikt voor de shuffle, maar random kan meer. Gebruik random ook om:
- de fruitmachine willekeurige rollen kan laten zien. Het makkelijkst is om de rollen in een lijst in een constante te definieren en daar een willekeurige waarde uit te kiezen.
- ook roulette moet nu `random` gebruikt worden om te bepalen waar het balletje terecht komt (de spin). We gaan dus niet meer een rare berekening met `round_number` gebruiken.


### 3. Datumverwerking
De geboortedatum uit week 5 moet voortaan netjes worden verwerkt met een functie uit de `datetime` standaardbibliotheek. Gebruik dus geen handmatige `split()`-logica meer. Je moet de geboortedatum omzetten naar een echte datum, zodat leeftijd tot op de dag nauwkeurig kan worden berekend. Een string omzetten naar een datum, kun je doen met `datetime.strptime` of `datetime.isoformat`.

Vergeet niet om uiteindelijk ook een `requirements.txt` te maken.

## Output
Je kunt de output bijvoorbeeld zo opbouwen:

```text
Wat is je naam? Bond
Wat is je geboortedatum? (dd-mm-yyyy) 11-11-1921
Wat is je gender? (m/v/x) m
Met hoeveel geld begin je in Casino de Gouden Driehoek? € 1000000
┌───────────────────────── Casino de Gouden Driehoek ─────────────────────────┐
│ Welkom, meneer Bond                                                         │
│                                                                             │
│ Startbudget: € 1000000.00                                                   │
│ Vaste kosten: € 16.50                                                       │
│ Saldo: € 999983.50                                                          │
│                                                                             │
│ Je hebt nog genoeg budget voor toegang tot het casino.                      │
└─────────────────────────────────────────────────────────────────────────────┘
┌─ Casino de Gouden Driehoek - hoofdmenu ─┐
│ ┌────────────────┬────────────────────┐ │
│ │ Optie          │ Actie              │ │
│ ├────────────────┼────────────────────┤ │
│ │ 1              │ Spellen            │ │
│ │ 2              │ Saldo              │ │
│ │ 3              │ Account            │ │
│ │ 0              │ Stop               │ │
│ └────────────────┴────────────────────┘ │
└─────────────────────────────────────────┘
Kies een optie: 1
┌─ Casino de Gouden Driehoek - spellen ─┐
│ ┌────────────┬──────────────────────┐ │
│ │ Optie      │ Spel                 │ │
│ ├────────────┼──────────────────────┤ │
│ │ 1          │ Fruitmachine         │ │
│ │ 2          │ Roulette             │ │
│ │ 3          │ Blackjack            │ │
│ │ 0          │ Terug                │ │
│ └────────────┴──────────────────────┘ │
└───────────────────────────────────────┘
Kies een spel: 1
┌───────────────── Casino de Gouden Driehoek - fruitmachine ──────────────────┐
│ Huidig saldo: € 999983.50                                                   │
└─────────────────────────────────────────────────────────────────────────────┘
Druk op enter om te spelen of typ stop om terug te gaan: 
Je inzet: € 2
┌────────────────────────────────── Output ───────────────────────────────────┐
│ Rollen: citroen | ster | kers                                               │
└─────────────────────────────────────────────────────────────────────────────┘
Geen match. Je verliest € 2.00
Nieuw saldo: € 999981.50
```

[//]: # (Todo: de randvoorwaarden en stappen nog uitwerken.)
## Randvoorwaarden
- Je gebruikt Rich om opmaak toe te voegen aan je bestaande printouts.
- Je gebruikt `random` in alle spellen, zodat de game uitkomsten echt willekeurig zijn.
- Je verwerkt geboortedata met een datumfunctie uit de standaardbibliotheek, in plaats van met `split()`.


## Stappenplan
1. Neem de bestaande structuur van week 5 over, zodat het hoofdmenu, de spellen en het accountgedeelte blijven bestaan.
2. Vind de Rich library op Pypi [link](https://pypi.org/project/rich/). 
3. Installeer Rich met pip in je project venv.
4. In `main.py` gebruik je Panel, Console en Table. Als globale constante maak je een `console = Console()` (dit is een klasse). In elke show_menu functie maak je een `table = Table(expand=True)`. Voeg vervolgens twee kolommen toe aan die table, met de `table.add_column` methode. Noem de kollomen "optie" en "actie"/"spel". Het printen doe je met `console.print()` waarin je (genest) `Panel.fit()` aanroept, waarbij je vervolgens de gemaakte tabel en `title="{title}"` als parameters meegeeft. 
5. Gebruik ook dezelfde Table en print techniek als in de vorige stap bij de `show_all_players` en `show_roulette_options` functies.
6. Gebruik `console.print(Panel(title={title}, {message}))` op alle plekken waar de titel (Casino de Gouden Driehoek) wordt geprint, of waar spel uitkomsten worden geprint. Bij spel uitkomst, mag je de titel "Ouput" gebruiken. Doe dit in: 
   - `initialize_player` - De welkomstberichten
   - `play_roulette` - De uitkomst
   - `show_hand` - De kaarten in een hand
   - `play_blackjack` - Het intro bericht met saldo en het afsluitende bericht met meerdere player en dealer saldo, totaal en resultaat.
   - `play_fruitmachine` - De uitslag
7. Vervang alle andere `print()` statements in je project door `console.print()`, waarbij je naar eigen inzicht markup kunt toepassen. Lees [hier](https://rich.readthedocs.io/en/latest/markup.html#syntax) hoe de syntax van de console markup werkt en welke [kleuren](https://rich.readthedocs.io/en/latest/appendix/colors.html#appendix-colors) je kunt gebruiken. Doe dit niet alleen in `main.py`, maar overal waar print statements staan.
8. Importeer de `choice` functie uit de `random` library in `fruitmachine.py`. 
9. Maak een constante met een lijst van minstens 5 "symbolen", zoals de strings kers, citroen en ster.
10. Gebruikt de `choice()` om drie willekeurige strings uit de zojuist gemaakte lijst te kiezen en return deze drie willekeurig gekozen symbolen als een tuple.
11. Verwijder alle verwijzingen naar de `round_number` variabele uit `fruitmachine.py`
12. Importeer de `randint()` functie uit de `random` library in `roulette.py`.
13. Gebruik `randint` om de `spin` mee te bepalen door een willekeurig getal tussen de 0 en 36 te selecteren.
14. In `profiles.py` pas je de `calculate_age` functie aan zodat deze gebruik maakt van een echte datum en ook op de dag nauwkeurig bereknd of de gebruiker 18+ is. Maak een `birthdate_value` variabele. Deze geef je de waarde van `datetime.strptime()`. Deze functie verwacht twee parameters: de datum (birthdate) en de format [("%d-%m-%Y")](https://docs.python.org/3/library/datetime.html#strftime-and-strptime-format-codes). Dit levert je een "datetime" object ook, maar daarvan heb je alleen de "date" nodig. Plak er daarom nog eens de `date()` methode bij achter.
15. Maak ook een `today_value` variabele. Dit doe je met `date.today`.
16. Als de `birthdate_value` hoger is dan de `roday_value`, mag je een `ValueError` raisen met het bericht dat de geboortedatum niet in de toekomst mag liggen.
16. Bereken nu de of de leeftijd van de gebruiker met de som: `huidig_jaar - birthday_jaar`
17. Bereken of de verjaardag dit jaar al is geweest door te kijken today_month en today_day kleiner zijn dan birthday_month en birthday_day. Als dat zo is, mag je 1 van de leeftijd aftrekken.
18. Maak een `requirements.txt` door het commando `pip freeze > requirements.txt` uit te voeren in je terminal.



