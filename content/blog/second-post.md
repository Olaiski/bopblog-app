---
title: Research and Discovery + Sprint 1 
description: Sprint 1 er ferdig! Litt info om hvordan det har gått.
slug: second-post
img: roguetest.png
---

# Research and Discovery<br/>
Vi har nå gjennomført en god del relevante moduler i Unity Learn (https://learn.unity.com/), 
de var for det meste i 3D men var fortsatt relevant for 2D utvikling. 
Disse modulene ga oss et greit innblikk i selve spillmotoren og en grunnleggende forståelse 
for hvordan man strukturer et prosjekt i Unity.
<br><br/>

# Sprint 1 (10.02.2021 - 20.02.2021)
Den første spriten tok for seg å finne passende figurer, tilesets og sprites. Disse ble hentet/kjøpt
fra [Unity Assets store](https://assetstore.unity.com/) og  [Itch.io](https://itch.io/).
I følge vårt Gantt Chart skulle vi også implementere lyd denne sprinten, men vi har utsatt dette for å lage mer rom
til å fin pusse på kamp- og helsesystemet. Vi vil prioritere spill-logikk og struktur fremfor lyd, men skal
implementere dette i en senere sprint.
<br><br/>

### Spillerkarakteren
Spillerkarakteren vi valgte kom med animasjoner (eller flere bilder vi måtte sette sammen til en animasjon).
Den hadde også angrep for nærkamp, samt et "ranged" angrep. Bildet under viser figuren.
<br><br/>
<img src="https://i.imgur.com/IJmKl1p.png" width="200px" height="200px" />
<br><br/>

Vi har også startet med å implementere et helsesystem, og et angrepsområde for spilleren.
Når man angriper sjekker den hva som er innenfor dette
området. Er det en fiende gjør man da skade til den.

<img src="https://i.imgur.com/VPM2f2g.png" width="400px" height="200px" />
<img src="https://i.imgur.com/6arxMQt.png" width="200px" height="200px" />
<br><br/>


### Tilesets
Spillet vårt er 2D-tilemap-basert, dvs. et spill der nivåene består av mange små "ruter" som samlet 
danner et rutenett av tiles. Noen ganger kan skillet mellom hver tile være åpenbart, men det kan også være sømløst og
ugjenkjennelig for spillerne.

Vi har valgt en god del forskjellige miljøer for spillverdenen vår. Vi skal ikke nødvendigvis bruke alt, men
man finner ofte små detaljer i de fleste man kan bruke (f.eks. en type plattform eller bakgrunn).

<br><br/>
<img src="https://i.imgur.com/yKwFXrE.png" width="500" height="200px" />
<br><br/>

Disse må "klippes" opp for å brukes gridsystemet, og plattformene må tilpasses til hvor spilleren/objekter kan stå. 
Bildene under viser noen plattformer er "klippet" ut og tilpasset en fysisk form (venstre), 
og det andre bildet (høyre) viser bruken av disse i gridsystemet. 
<br><br/>
<img src="https://i.imgur.com/CP9Drpy.png" width="300" height="200px" />
<img src="https://i.imgur.com/wjbDXWJ.png" width="300" height="200px" />
<br><br/>

### Fiender
Akkurat nå har vi bare valgt ut 2 typer fiender, én for nærkamp og én som skyter projektiler. 
Vi blir å finne flere sprites etc. forløpende basert på de forskjellige AI atferdene.
<br><br/>
<img src="https://i.imgur.com/RPj0M81.png" width="300" height="200px" />
<br><br/>


### Veien videre
Neste sprint tar for seg fiende AI / patruljering, animasjoner og et "Tutorial område".
