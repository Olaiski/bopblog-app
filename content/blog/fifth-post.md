---
title: Sprint 4
description: Sprint 4 - Abomination (Mini-boss), Nye Fiender og Pickups 
slug: fifth-post
img: Abomination.png
createdAt: 5
---

# Sprint 4 (30.03.2021 - 20.04.2021)
Denne sprinten tok for seg implementering av Mini-boss, Nye Fiender, "Pickups" (Heart, Coin, Key), Dører og Gulv. 
Planen var å bygge videre på kartet (helt nytt nivå), men dette var vi nødt til å utsette.

<br><br/>


### Pickups
<img src="https://i.imgur.com/L8vF87j.png" width="20" height="20" />
<img src="https://i.imgur.com/K7spxy8.png" width="20" height="20" />
<img src="https://i.imgur.com/gTw5gBm.png" width="20" height="20" />

Pickupsystemet er på plass. Heart og Coin har en viss sjanse til å droppe fra fiender når de dør. Abomination (Mini-boss) dropper Key, 
denne trenger spilleren for å komme videre i spillet.



<br><br/>
### Abomination (Mini-boss)
Denne fienden finnes det bare én av, den er ment å være vanskeligere enn de andre fiendene. For at spilleren skal komme seg 
videre i spillet må hen drepe denne “Mini-bossen”, dette er fordi den legger ifra seg en nøkkel som spilleren trenger for å åpne en lukket dør.
<br></br>
Her fikk vi tatt i bruk GameManager skriptet (Dette skriptet holder styr på permanente endringer i et nivå, som f.eks. at denne «bossen» ikke skal kan drepes 2 ganger. )

Denne fungerer veldig likt de andre fiendetypene, med noen unntak. Den her litt mer helse, man blir tvunget til å slåste med den (sperrer utveien) og 
den har spesialangrep.

GIF'en under viser spesialangrepet og nøkkelen som dropper.
<br><br/>
<img src="https://i.imgur.com/Tn5AHLy.gif" width="350" height="200" />
<br><br/>

GIF som viser døren man trenger nøkkel for å åpne.
<br><br/>
<img src="https://i.imgur.com/7uRB5LW.gif" width="350" height="200" />
<br><br/>

### Nye Fiender!
I løpet av prosjektet har vi fått venner til å prøvespille builds. Vi fikk kommentarer på at det føltes veldig monotont å 
slåss mot de to samme fiendene (Cultist, JumpAttacker) hele tiden. På grunn av dette valgte vi å implementert flere fiendetyper, og
nå er de fleste av de ferdige!
<br><br/>
#### 1. FlyingBatPassive
FlyingBatPassive er en fiende som ikke har egne angrep, den eneste måten den kan gjøre skade på er å kollidere med spilleren.

<img src="https://i.imgur.com/AhRLz7n.png" width="100" height="100" />

#### 2. FlyingBatShooter 
FlyingBatShooter er en litt mer avansert variant av FlyingBatPassive, i tillegg har den en radius kalt shootingRange. 
Hvis spilleren er innenfor denne radiusen vil fienden slutte å bevege seg, men starte å skyte kuler på spilleren. 

<img src="https://i.imgur.com/JtcKylL.png" width="100" height="100" />

#### 3. CircleBat 
CircleBat beveger seg mellom X antall faste punkter som er lagd på forhånd.
Hvis spilleren er innenfor lineOfSight radius til CircleBat så vil den starte en angrepsskript som roterer to ulike angrep.

<img src="https://i.imgur.com/Cm30yA5.png" width="100" height="100" />

#### 4. Static Statue
Static Statue er en fiende uten noen form for bevegelighet. Den skyter kuler basert på avstanden (kort- og lang-distanse angrep).

<img src="https://i.imgur.com/z1v3Ebm.png" width="240" height="200" />

<br><br/>
#### 5. PlatformHugger
PlatformHugger er en fiende som beveger seg mellom X antall punkter som er satt på forhånd i scenen. Den har ingen helse og er derfor umulig for spilleren å ødelegge.

<img src="https://i.imgur.com/hL35qoF.png" width="300" height="150" />

<br><br/>
#### 6. Crossbow Cultist
Cultist Crossbow er en statisk fiende som har et langdistanseangrep.

<img src="https://i.imgur.com/SoNUHT1.png" width="700" height="120" />
