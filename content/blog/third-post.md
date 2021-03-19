---
title: Sprint 2
description: Sprint 2 er over, vi har impl. AI og Tutorial level!
slug: third-post
img: ai2.png
---
# Sprint 2  (20.02.2021 - 09.03.2021)
Denne sprinten tok for seg implementering av fiender / AI og ferdigstilling av et "Tutorial-område". Vi
ligger fortsatt litt etter når det gjelder lyd, vi prioriterte å utvikle flere typer fiender.
<br><br/>

### Cultist
Den ene fienden vi har implementert med animasjoner og AI er en "Cultist", han baserer seg på nærkamp og 
patruljerer mellom 2 punkter. Han "ser" spilleren når hen kommer innenfor en "Trigger Area" og begynner så 
å følge etter spilleren. Klarer spilleren å komme seg ut fra "HotZone" går han tilbake i en patruljerings "state".
Gif'en under viser dette.
<br><br/>
<img src="https://i.imgur.com/vmSiGup.gif" width="500" height="200" />
<br><br/>

"Kollisjons-boxene" og "Hit-boxene" må også følge animasjonen til fiendene, dette må gjøres for hvert bilde 
i animasjonene, noe som kan ta litt tid. I GIF'en under kan man se angreps animasjonen til fienden.
 <br><br/>
<img src="https://i.imgur.com/ZFJ7wua.gif" width="400" height="300" />
<br><br/>


Vi har flere type fiender men velger å ikke vise alle pga. tid, kanskje vi laster opp noen flere videoer på et senere
tidspunkt.

### Helsesystem
\
Måten vi håndtere helsesystemet for fienden er ved å sette en max verdi for hver av de, og hvis spilleren treffer minker helsen med en fastsatt verdi.
På spiller objektet er det en "OverlapCircle" som sjekker om det er en fiende i samme "layer" når hen angriper.

``` csharp
 public void Attack(int amount)
    {
        // ++
        // Sjekker om fiender er innenfor rekkevidde
        Collider2D[] hitEnemies = Physics2D.OverlapCircleAll(attackPoint.position, attackRange, enemyLayers);
        // Gjør skade 
        foreach (Collider2D enemy in hitEnemies)
            StartCoroutine(WaitForAttackDamage(enemy));   
    }
```
<br><br/>
For at spilleren skal ta skade har vi satt opp et Pub/Sub-pattern, der spilleren abonnerer på TakeDamageEvent og kobler dette opp mot sin egen TakeDamage metode. 
Og når en fiende gjør skade på spilleren så sendes det et varsel til DamageBroker, som igjen vil varsle sine abonnenter(I dette tilfellet spilleren). 
Dette gjør at fienden og spilleren er dermed uavhengig av hverandre.
 <br><br/>
<img src="https://i.imgur.com/6CoEMrT.png" width="400" height="250" />
<br><br/>

Koden under viser klassediagrammet for Pub/Sub-mønstret.
``` csharp
// DamageBroker klassen
public class DamageBroker
{
    public static event Action<int> TakeDamageEvent;
    public static void CallTakeDamageEvent(int damage)
    {
        TakeDamageEvent?.Invoke(damage);
    }
}
    
// Cultist (Hitbox), "del av cultist klassen"
public class CultistHitBox : MonoBehaviour
{
    private void OnTriggerEnter2D(Collider2D collision)
    {
        if (collision.name.Equals(PLAYER_NAME))
            DamageBroker.CallTakeDamageEvent(damageAmount);    
}

// Spiller klassen
public class Player : MonoBehaviour, IAttacker<int>, IDamageable
{
    // Spilleren tar skade
    public void TakeDamage(int damage)
    {
        currentHealth -= damage;
    
        if (currentHealth <= 0)
            Death();
    }
    // Event lytter når objektet blir aktiv
    private void OnEnable()
    {
        DamageBroker.TakeDamageEvent += TakeDamage;
    }
    // Slå av lytter når objektet blir inaktivt (Memory leaks)
    private void OnDisable()
    {
        DamageBroker.TakeDamageEvent -= TakeDamage;
    }
}
```
<br><br/>
### Tutorial område
\
For at spilleren skal bli kjent med hvordan man styrer karakteren har vi valgt å lage en kort introduksjon
med noen lette fiender og en grafisk visning for input. Under ser man et bilde av hele brettet + UI.
 <br><br/>
<img src="https://i.imgur.com/qRCDN1t.png" width="700" height="500" />
<br><br/>


### Neste steg i utviklingen
Neste sprint skal vi fokusere mer på nivå-design, forskjellige "miljø-objekter" som heiser og dører. 
