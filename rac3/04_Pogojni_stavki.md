# Pogojni stavki

Pogojni stavki so ukazi s katerimi implementiramo odočanje. Računalniku povejo pod katerim pogojem naj izvede dano kodo.

Java pozna dva pogojna stavka - IF in SWITCH. Preden pa se ju naučimo uporabljati, moramo razumeti pogojne operatorje.

> **Blok kode** je vedno omejen z zavitimi oklepaji `{}`. Izjemoma jih lahko izpustimo, če blok obsega samo en ukaz.

## Pogojni operatorji

Pogojni operatorji nam omogočajo primerjanje podatkov in sestavljanje pogojnih stavkov. Lahko bi rekli, da nam podajo način pretvorbe podatkov vseh oblik v binarno vrednost `true` ali `false`.

Osnovni pogojni operatoji, ki nam omogočajo primerjavo veličin so:

| Operacija        | Operator | Primer                       |
| ---------------- | :------: | ---------------------------- |
| Ekvivalenca      |   `==`   | `4 % 2 == 0` $\lrArr$ `true` |
| Večje            |   `>`    | `5 > 5` $\lrArr$ `false`     |
| Večje ali enako  |   `>=`   | `5 >= 5` $\lrArr$ `true`     |
| Manjše           |   `<`    | `5 < 3` $\lrArr$ `false`     |
| Manjše ali enako |   `<=`   | `5 <= 3` $\lrArr$ `false`    |

Da pa z njimi sestavimo bolj kompleksne pogoje, potrebujemo še dva operatorja:

| Operacija | Operator | Primer                            |
| --------- | :------: | --------------------------------- |
| IN (AND)  |   `&&`   | `true && false` $\lrArr$ `false`  |
| ALI (OR)  |  `\|\|`  | `true \|\| false` $\lrArr$ `true` |

Ko spoznamo objekte, bomo spoznali še operator `instanceof`.

## Stavek IF

Najbolj osnovna oblika kontrole toka programa je pogojni stavek **IF**, ki omogoča izvajanje bloka kode na podlagi izpolnjenega pogoja.

V spodnjem primeru primerjamo vrednost spremenljivke `starost` s konstanto `18`.

```java
int starost = 16;

// Če je starost večja ali enaka 18,
//   Izpiši "Uporabnik je polnoleten!"

if (starost >= 18) {
	System.out.println("Uporabnik je polnoleten!");
}
```

V primeru, da želimo izvesti pogojno kodo kadar pogoj ni izpolnjen, lahko stavek IF dopolnimo s stavkom **ELSE**. Ta izvede blok kode, če pogoj stavka IF ni izpolnjen - tj. je `false`.

```java
if (starost >= 18) {
	System.out.println("Uporabnik je polnoleten!");
} else {
	System.out.println("Uporabnik NI polnoleten!");
}
```

Za še več opcij pa lahko dodamo tudi stavek **ELSE IF**. Ta nam omogoča navedbo še enega pogoja, ki se preverja samo v primeru, da je prejšnji pogoj ni bil izpolnjen.

Pravilnost pogojev se torej vedno izvaja od vrha navzdol in prekine, ko se izpolni prvi pogoj, ali dosežemo ELSE. Takrat izvedemo blok kode, ki pripada danemu pogoju.

```java
if (starost >= 40) {
	System.out.println("Uporabnik je srednjih let ali starejši.");
} else if (starost >= 30) {
	System.out.println("Uporabnik je v tridesetih letih starosti.");
} else if (starost >= 20) {
	System.out.println("Uporabnik je v dvajsetih letih starosti.");
} else if (starost >= 18) {
	System.out.println("Uporabnik je polnoleten! A še vedno najstnik.");
} else {
	System.out.println("Uporabnik NI polnoleten!");
}
```

### Krajša verzija

Obstaja tudi krajši zapis (oklepaji v primeru so opcijski):

```java
String odgovor = (starost >= 18 ? "JE polnoleten" : "NI polnoleten");
```

Sestavljen je po sledečem modelu: `<pogoj> ? <true> : <false>`.

## Stavek SWITCH

Ko primerjamo vse možne vrednosti dane spremenljivke, pa je boljša izbira stavek **SWITCH**. Pri tem namreč določimo spremenljivko, za katero preverjamo enakost s konstantami v bloku SWITCH stavka.

Spremenljivka, ki jo primerjamo, mora biti tipa _byte_, _short_, _char_ ali _int_, v novejših verzijah Jave pa tudi _String_ ali _enum_.

Znotraj telesa stavka določimo kodo, ki se izvede za vsak možen primer s stavkom **CASE**. Ko zaključimo kodo za dan primer, uporabimo stavek **BREAK**, dručače se izvedejo še vsi naslednji primeri (to je glavni kontrast z IF stavkom).

V primeru, da spremenljivka vsebuje vrednost za katero nismo definirali primera, lahko uporabimo stavek **DEFAULT**, kjer določimo kodo za vse nedefinirane primere.

```java
int stMeseca = 6;
String mesec;

switch (stMeseca) {
	case 1:
		monthString = "January";
		break;
	case 2:
		monthString = "February";
		break;
	case 3:
		monthString = "March";
		break;
	case 4:
		monthString = "April";
		break;
	case 5:
		monthString = "May";
		break;
	case 6:
		monthString = "June";
		break;
	case 7:
		monthString = "July";
		break;
	case 8:
		monthString = "August";
		break;
	case 9:
		monthString = "September";
		break;
	case 10:
		monthString = "October";
		break;
	case 11:
		monthString = "November";
		break;
	case 12:
		monthString = "December";
		break;
	default:
		monthString = "Neveljaven mesec";
		break;
}
```
