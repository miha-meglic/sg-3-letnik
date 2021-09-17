# Interakcija s konzolo

Da lahko začnemo s pisanjem celovitih programov, se bomo najprej naučili branja in pisanja v konzolo oz. terminal.

Preden začnemo z ukazi se še enkrat spomnimo, da Java **ločuje med malimi in velikimi črkami**.

## Pisanje

Za pisanje bomo spoznali dva osnovna ukaza - pisanje in pisanje z novo vrstico.

S spodnjim ukazom lahko preprosto izpišemo katero koli spremenljivko ali besedilo v konzolo. Preprosto zamenjamo `s` med oklepaji z vrednostjo, ki jo želimo izpisati.

```java
System.out.print(s);
```

Hitro pa bomo opazili, da če stavek izvedemo večkrat, se izpisi pojavljajo drug poleg drugega, brez presledkov ali novih vrstic. Da bi dobili vsak izpis v svoji vrstici, uporabimo manjšo variacijo - pisanje z novo vrstico.

Ta ukaz deluje identično zgornjemi, le da po izpisu pomakne kurzor v novo vrstico - kot bi pritisnili tipko enter v urejevalniku besedila.

```java
System.out.println(s);
```

Posebna lastnost je, da pisanje z novo vrstico lahko uporabimo tudi brez podajanja parametra `s`, kar bo preprosto premaknilo kurzor v novo vrstico.

## Branje

Branje je bolj kompleksna izmed operacij, saj zahteva nekaj priprave in uvažanje paketa.

Najprej moramo torej na vrhu datoteke - pred definicijo razreda, kjer želimo uporabljati branje dodati stavek:

```java
import java.util.Scanner;
```

V začetku programa pa bomo ustvariti spremenljivko, preko katere bomo brali. Torej v začetku vaše metode `main`, bomo dodali:

```java
Scanner scn = new Scanner(System.in);
```

Tu je vredno pripomniti, da premenljivko lahko poimenujemo poljubno, a v primerih bom uporabljal ime `scn`.

Branje ima v kontrastu s pisanjem tudi veliko več različnih funkcij, ki določajo ali beremo besedo, vrstico, celo število ali decimalno število. Najbolj enostavna in, za nas, najbolj uporabna bosta branje besede in branje celega števila - ostalo bomo spoznali kasneje.

Branje besede (in shranjevanje le te v spremenljivko) izvedemo na sledeč način:

```java
String beseda = scn.next();
```

Spet je ime spremenljivke poljubno, v tem primeru sem uporabil `beseda`.

Branje celega števila pa zelo podobno (spet poljubno ime spremenljivke):

```java
int stevilo = scn.nextInt();
```

Ostale metode sledijo istemu kopitu.  
Celotna dokumentacija za `Scanner` je na voljo na [tej povezavi](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/util/Scanner.html).
