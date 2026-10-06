# [4-Way-Traffic] - [Kategori, Crypto]
**Poeng:** 430
**Vanskelighetsgrad:** Medium
**Konkurranse:** CTFkom 30.09.2026

## Beskrivelse
Oppgaven ga ut en wireshark fil ('challenge') hvor flagget var gjemt blant de ulike pakkene, hvor man skulle undersøke disse for å finne flagget som var delt opp i ulike biter.

Tipset i oppgaven var: 
Flagget er delt opp i ulike biter, kan du finne disse og sette de riktig sammen?


## Analyse
Jeg startet med å se gjennom pakkene i opptaket for å få oversikt over trafikken. Underveis oppdaget jeg at én av TCP-pakkene inneholdt en bit som skilte seg ut fra resten, noe som tydet på at flagget var skjult i TCP-trafikken.

## Løsning
For å finne resten av flagget filtrerte jeg på tcp i Wireshark, slik at bare TCP-pakkene ble vist. Deretter sorterte jeg pakkene etter lengde (Length-kolonnen). Da kom bitene i riktig rekkefølge, og jeg kunne sette dem sammen til det fullstendige flagget: [flagg her].

**Flagg:** CTFkom{4nalyzing_traff1c_is_c00l}
