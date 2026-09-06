# [Invisible Ghost] - [Kategori, Stegonography]
**Poeng:** 200
**Vanskelighetsgrad:** Lett
**Konkurranse:** CTFkom 02.09.2026

## Beskrivelse
I think there is some text in this image but I'm not able to read it. Are you?

## Analyse
- Det skal finnes skjult tekst i bildet
- Teksten er ikke synlig med det blotte øyet ("usynlig" - derav navnet "Invisible Ghost")
- Man skal finne denne skjulte teksten
- Flagget skal skrives på formatet CTFkom{...}

## Løsning
Jeg åpnet bildet som fulgte med oppgaven. I oppgaveteksten sto det at det skulle finnes tekst i bildet, men at den ikke var mulig å lese med det blotte øyet. Dette tydet på at teksten var skjult ved hjelp av svake fargeforskjeller, altså en enkel form for steganografi.
For å avdekke teksten skrudde jeg opp lysstyrken og kontrasten på bildet i et bildebehandlingsprogram. Da kom den skjulte teksten tydelig frem, siden den opprinnelig hadde en farge som lå veldig nære bakgrunnsfargen og dermed var vanskelig å se med normale innstillinger.
Ved å justere disse verdiene klarte jeg å lese teksten, som ga meg flagget på formatet CTFkom{...}.

## Flag
CTFkom{alm0st_1nv1sibl3_t3xt_903ufd0t34+}

Relevante skjermbilder:
Oppgave bildet <img width="1348" height="1348" alt="ghost" src="https://github.com/user-attachments/assets/04964aa0-c4b9-4490-b3c7-fd1c87d582f4" />
Løst oppgave bildet <img width="1348" height="1348" alt="ghost_Løst" src="https://github.com/user-attachments/assets/4add45aa-4823-4c7f-85b6-cfaf276b5cd5" />

