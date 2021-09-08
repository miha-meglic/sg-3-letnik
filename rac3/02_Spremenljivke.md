# Spremenljivke

**Spremenljivka** je pomnilniška lokacija s simboličnim imenom, ki vsebuje vrednost definiranega tipa.  
_Koncept je identičen kot v matematiki, tj. spremenljivka je simbol, ki predstavlja neko vrednost._

Kot omenjeno, imamo več tipov spremenljivk. Najbolj osnovni med njimi so:

- **celo število** (_ang. integer number_)
- **decimalno število** (_ang. floating-point number_)
- **znak** (_ang. character_)
- **logična vrednost** (_ang. boolean value_)

Ko v Javi ustvarimo spremenljivko ji moramo določiti **tip**, **ime** in **vrednost**.  
Spremenljivke lahko deklariramo tudi brez vrednosti. V tem primeru spremenljivka zavzame privzeto vrednost, ki je **0** za številske tipe in **null** za vse ostalo.

> **POZOR!** Ta mehanizem ne deluje z **lokalnimi spremenljivkami** (_spremenljivke, ki pripadajo trenutni metodi_), pri katerih moramo poskrbeti, da jim vrednost določimo oz. jih **inicializiramo** (_ang. initialize_) preden jih uporabimo.

```java
// Spremenljivka z določeno vrednostjo
int visina = 180;  // visina = 180

// Spremenljivka s kasnejšo inicializacijo
int starost;
starost = 16;  // *inicializacija*: starost = 16
```

## Konstante

Posebna vrsta spremenljivke je **konstanta**, ki se po inicializaciji ne mora spremeniti. V Javi jih definiramo s ključno besedo **final** pred tipom spremenljivke.

Ponovno je mogoča kasnejša inicializacija, a tokrat le za lokalne spremenljivke.

```java
final int TRI = 3;

// Kasnejša inicializacija
final int TRI;
TRI = 3;  // od tu je spremenljivka konstantna
```

## Konvencija imenovanja spremenljivk

**Java razlikuje velike in male črke**, torej so `test`, `Test` in `TEST` tri različne spremenljivke.

Imena spremenljivk naj se vedno začnejo s črko. Druga dovoljena začetna znaka sta `$` in `_`, vendar sta odsvetovana. Sledijo lahko črke, števke in zgornja znaka.

Spremenljivke se po dogovoru pišejo z malimi črkami ter veliko začetnico vseh besed razen prve - npr. `visina`, `telesnaVisina`.  
_S tujko tak zapis imenujemo **camelCase**._

Konstante se po dogovoru pišejo z velikimi črkami, besede pa ločimo s `_` - npr. `STEVILO_PI`.  
_S tujko tak zapis imenujemo **snake_case**._

Referenca: [Java Docs: Variables](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/variables.html)

## Prirejanje

Vsakič ko spremenimo vrednost spremenljivke, to imenujemo **prirejanje**.

```java
int starost;  // Deklaracija
starost = 16;  // Inicializacija

double visina = 180.5 // Definicija

starost = starost + 1;  // Prirejanje
```

Pri prirejanju spremenljivke računalnik vedno **najprej izračuna novo vrednost** (_izraz na desni strani enačaja_) ter nato **priredi spremenljivko**, kar nam omogoča npr. prištevanje lasntne vrednosti kot vidimo v zgornjem primeru.
