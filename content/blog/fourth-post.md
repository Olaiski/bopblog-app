---
title: Sprint 3
description: Sprint 3 - Feller, heiser og nivådesign!
slug: fourth-post
img: KillFloor2.png
createdAt: 4
---
# Sprint 3  (09.03.2021 - 30.03.2021)
Denne sprinten tok for seg implementering av feller, heiser og nivådesign. Vi ligger litt etter i nivådesign delen av spillet, 
dette grunnet sykdom. Vi tror vi skal klare å hente det inn igjen.
De fleste miljøobjekter har ikke "Sprites", dette er noe vi må se på senere. 
<br><br/>

### Feller
Feller er en mye brukt "miljøfiende" i metroidvania sjangeren, dette kan håndteres på mange måter. Vår implementasjon er relativt enkel og gjenbrukbar.
Vi sjekker om spilleren er innenfor et forhåndssatt område, hvis spilleren er det, trigger vi et event som dreper
hen momentant.
<br><br/>
<img src="https://i.imgur.com/g5ycQPT.gif" width="500" height="200" />
<br><br/>
Under kan du se koden som sjekker om spilleren treffer KillFloor.
 ``` csharp
    // KillFloor sjekk
    private void OnCollisionEnter2D(Collision2D col)
    {
        if (col.transform.CompareTag(PLAYER_TAG))
            EventManager.TriggerEvent(EnumEvents.KILL_FLOOR_HIT);
    }
 ```
<br></br>
En annen løsning er å lage "Prefabs" (Egendefinert Spillobjekt) basert på piggene, disse kan da "males" på
nivået (ved hjelp av 2D-extras pakken), på samme måte som plattformene. Men vi valgte en litt enklerer måte å håndtere dette, pga. tid.

<br><br/>
### Heiser
Heiser er også mye brukt i 2D-spill, de går som oftesest på de vertikale eller horisontale aksene. Den heisen vi har implementere går på den
vertikale.
<br><br/>
<img src="https://i.imgur.com/Qa98tif.gif" width="300" height="200" />
<br><br/>

Heisen baserer seg på en startposisjon og en sluttposisjon, disse blir hentet i det skriptet starter. Under kan du se en del av 
koden for å bevege heisen.
 ``` csharp
  private void Move()
    {
        // Beveger seg til et punkt (nextPos) fra nåværende punkt.
        trans.localPosition = Vector3.MoveTowards(trans.localPosition, nextPos, speed * Time.deltaTime);
        // Hvis heisen når punktet, endre retning
        if (Vector3.Distance(trans.localPosition, nextPos) <= 0.1)
            ChangeDestination(); 
    }
    private void ChangeDestination()
    {
        nextPos = nextPos != startPos ? startPos : endPos;
    }
 ```
<br><br/>
Det oppsto noen problemer ved den første iterasjonen av heisen. Spilleren og heisen har forskjellige hastigheter, dette resulterte i at
spilleren falt etter heisen når den var på tur ned.
<br><br/>
<img src="https://i.imgur.com/obqO64T.gif" width="200" height="200" />
<br><br/>

Vi fant ut at man kan sette spilleren som et barn av heis-objektet, da arver
spilleren hastigheten. Og problemet var løst!
 ``` csharp
  private void OnCollisionEnter2D(Collision2D collision)
     {
         if (collision.gameObject.CompareTag("Player"))
             collision.collider.transform.SetParent(trans);
     }
     private void OnCollisionExit2D(Collision2D collision)
     {
         if (collision.gameObject.CompareTag("Player"))
             collision.collider.transform.SetParent(null); 
     }
 ```

<br><br/>
### Nivådesign
Denne sprinten tok også for seg implementasjonen av "Castle_Level". Det er lagt opp til at spilleren skal støte på en "mini-boss", og andre
Metroidvania prinsipper som utforskning. 
Hvis man vil ha en detaljerik spillverden må man sette av en god del tid. Vi er greit fornøyd så langt med "Castle_Level", og vi må 
se hvor mye tid vi har til gode for å utvide med flere nivåer.  
<br><br/>
<img src="https://i.imgur.com/pOVfXGA.png" width="720" height="200" />
<br><br/>








