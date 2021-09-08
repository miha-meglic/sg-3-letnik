# Podatkovni tipi

**Podatkovni tip** je atribut spremenljivke, ki prevajalniku ali tolmaču pove, na kakšen način nameravamo podatek uporabiti.

## Primitivni tipi

### Logične vrednosti

Logične vrednosti zapisujemo s tipom `boolean`, ki izraža resničnost. Ima samo dve možni vrednosti: `true` in `false`.

### Cela števila

Java nam ponuja več tipov za hranjenje celih števil. Razlikujejo se samo po velikosti, tj. po številu bajtov, ki jih rezervirajo v pomnilniku.

| Tip   | Velikost [byte] | Min vrednost         | Max vrednost        |
| ----- | --------------- | -------------------- | ------------------- |
| byte  | 1               | -128                 | 127                 |
| short | 2               | -32768               | 32767               |
| int   | 4               | -2147483648          | 2147483647          |
| long  | 8               | -9223372036854775808 | 9223372036854775807 |
| char  | 2               | 0                    | 65535               |

Najpogosteje bomo uporabljali kar tip `int`. Manjši so uporabni samo, kadar želimo varčevati s pomnilnikom. Večji tip `long` pa za res velika cela števila.

### Realna števila

Java pozna dva tipa za hranjenje realnih števil oz. števil s plavajočo vejico. Razlikujeta se ponovno po velikosti.

| Tip    | Velikost [byte] | Natančnost         | Min [10^] | Max [10^] |
| ------ | --------------- | ------------------ | --------- | --------- |
| float  | 4               | 7 decimalnih mest  | -45       | 38        |
| double | 8               | 15 decimalnih mest | -324      | 308       |

> **Za navdušence:** računalnik hrani realna števila v formatu definiranim s standardom [IEEE 754](https://en.wikipedia.org/wiki/IEEE_754).  
> Video: [Computerphile](https://youtu.be/PZRI1IfStY0)

### Zanki

Znake zapisujemo s tipom `char`, ki predstavlja Unicode (_UTF-16_) znak. Vrednost zapišemo v enojne narekovaje - npr. `char znak = 'a'`.

## Niz znakov (_ang. string_)

Niz znakov zapišemo s tipom `String`, ki ne spada med primitivne tipe, saj je sestavljen iz več spremenljivk primitivnega tipa `char`.

> V Javi primitivne tipe in ključne besede hitro ločimo od objektov/razredov, ker so primitivni tipi in ključne besede vedno zapisane z malo začetnico, ostalo pa običajno z veliko.

Več o uporabi in manipulaciji nizov bomo spoznali kasneje zaenkrat pa samo primer:

```java
// Inicializacija
String ime = "Jaka";

// Združevanje
String pozdrav = "Živjo, " + ime;

// Izpis
System.out.println(pozdrav);
```

## Osnovne operacije

### Numerične operacije

Java pozna vse običajne numerične operacije (seštevanje, odštevanje, množenje in deljenje) in operacijo modulo, ki vrne ostanek pri deljenju števila.

Vrstni red operatorjev je enak kot v matematiki. Modulo operator je enakovreden množenju in deljenju. Kot v matematiki, lahko uporabljamo oklepaje da spremenimo vrstni red operacij.

| Operacija  | Račun | Primer      |
| ---------- | :---: | ----------- |
| Seštevanje | a + b | `2 + 3 = 5` |
| Odštevanje | a - b | `3 - 2 = 1` |
| Množenje   | a * b | `2 * 3 = 6` |
| Deljenje   | a / b | `4 / 2 = 2` |
| Modulo     | a % b | `8 % 3 = 2` |

> **POZOR!** Tip rezultata v Javi je odvisen od tipa vhodnih podatkov. Vedno zavzame bolj natančno izmed vhodnih, tj. če je eden od vhodov decimalno število, bo izhod decimalno število.

```java
int a = 7;
int b = 2;
int c;

c = a + b;  // c = 9
c = a - b;  // c = 5
c = a * b;  // c = 14
c = a / b;  // c = 3 !Ker uporabljamo cela števila!
c = a % b;  // c = 1

c = a / 2.0  // c = 3.5
c = 7.0 / b  // c = 3.5
```

#### Krajši zapis

Kadar želimo spremenljivki prišteti, odšteti, ... neko drugo število (oz. spremenljivko), imamo za to dva možna zapisa.

```java
int a = 7;

// Običajni zapis
a = a + 3;
a = a - 2;
a = a * 6;
a = a / 4;
a = a % 8;

// Krajši zapis
a += 3;
a -= 2;
a *= 6;
a /= 4;
a %= 8;
```

#### Celoštevilske operacije

Za prištevanje in odštevanje celih števil pa obstaja še krajši zapis.

```java
int a = 3;

// Prištevanje enice
a++;  // a = 4
a++;  // a = 5

// Odštevanje enice
a--;  // a = 4
```

### Bitne operacije

V Javi je mogoče s števili operirati tudi na nivoju bitov.

Poznamo sledeče operacije:

| Operacija         |  Zapis  |       Primer        |
| ----------------- | :-----: | :-----------------: |
| Arit. pomik levo  | a << b  |  1011 << 1 = 0110   |
| Arit. pomih desno | a >> b  |  1011 >> 1 = 1101   |
|                   |         |  0111 >> 1 = 0011   |
| Log. pomik desno  | a >>> b |  1011 >>> 1 = 0101  |
| Negacija          |   ~a    |    ~1011 = 0100     |
| IN                |  a & b  | 1011 & 0110 = 0010  |
| ALI               | a \| b  | 1010 \| 1100 = 1110 |
| Ekskluzivni ALI   |  a ^ b  | 1011 ^ 1101 = 0110  |

> Te operacije niso del snovi (ne bodo na testu), so pa občasno uporabne.
