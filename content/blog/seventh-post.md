---
title: Bug fixes!
description: Rettet opp i noen bugs
slug: seventh-post
img: software-762486_640.jpg
createdAt: 7
---
# Bugs Bugs Bugs, Fix Fix Fix!
Prosjektet er egentlig over, men vi hadde lyst til å rette opp i noen bugs.

<br></br>
# Savesystem & Scene Transition
Dette systemet var ikke helt optimalt når vi leverte oppgaven, så vi satt oss ned dagen etter for å rette opp i feilen.
Når spilleren nå går fra scene til scene, lagrer vi helse og posisjonen hen var i. Dette er for å håndtere sceneskifte tilbake, uten dette blir
spillerens posisjon satt til startposisjonen til scenen. 


<img src="https://i.imgur.com/8RGrQFD.gif" width="350" height="200" />
<br><br/>


Vi måtte også håndtere posisjonen til spilleren når hen dør, her skal man returnere til startposisjon.


<img src="https://i.imgur.com/i0XgFeH.gif" width="350" height="200" />




