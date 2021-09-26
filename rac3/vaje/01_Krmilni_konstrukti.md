# Vaje: Krmilni konstrukti

## 1. Kvadrati

Napišite program, ki prebere celi števili `a` in `b` in izpiše kvadrate vseh velih števil od `a` do (vključno) `b`.

### Primer

**Vhod:**

```text
5 8
```

**Izhod:**

```text
25
36
49
64
```

### Rešitev

<details>
<summary><i>Program.java</i></summary>

```java
import java.util.Scanner;

class Program {
	public static void main (String[] args) {
		Scanner scn = new Scanner(System.in);

		// Preberemo vhod iz konzole
		int a = scn.nextInt();
		int b = scn.nextInt();

		// Izpisemo kvadrate
		for (int i = a; i <= b; i++) {
			System.out.println(i * i);
		}
	}
}
```
</details>

## 2. Število števk

Napišite program, ki prebere celo število in izpiše število njegovih števk.

### Primer

**Vhod:**

```text
730545
```

**Izhod:**

```text
6
```

### Namig

Da celemu številu odstranimo najbolj desno števko, ga lahko delimo z 10.

### Rešitev

<details>
<summary><i>Program.java</i></summary>

```java
import java.util.Scanner;

class Program {
	public static void main (String[] args) {
		Scanner scn = new Scanner(System.in);
		
		// Preberemo vhod iz konzole
		int a = scn.nextInt();
		// Pripravimo spremenljivko za belezenje stevk
		int stevec = 0;

		// Prestejemo stevke
		while (a > 0) {
			// Zabelezimo stevko
			i++;
			// Odstranimo najbolj desno stevko
			a = a / 10;
		}

		// Izpisemo rezultat
		System.out.println(i);
	}
}
```
</details>

## 3. Izpis števk

Napišite program, ki prebere celo število in izpiše njegove števke v obratnem vrstnem redu (vsako v svojo vrstico).

### Primer

**Vhod:**

```text
730545
```

**Izhod:**

```text
5
4
5
0
3
7
```

### Namig

Da iz celega števila dobimo najbolj desno števko, lahko uporabimo ostanek pri deljenju z 10.

### Rešitev

<details>
<summary><i>Program.java</i></summary>

```java
import java.util.Scanner;

class Program {
	public static void main (String[] args) {
		Scanner scn = new Scanner(System.in);
		
		// Preberemo vhod iz konzole
		int a = scn.nextInt();

		// Prestejemo stevke
		while (a > 0) {
			// Izpisemo najbolj desno stevko
			System.out.println(a % 10);
			// Odstranimo najbolj desno stevko
			a = a / 10;
		}
	}
}
```
</details>

## 4. Collatzovo zaporedje

Collatzovo zaporedje pričnemo s podanim celim številom `n`, nato pa ponavljamo sledeči postopek, dokler ne pridemo do števila 1:

- če je trenutno število sodo, ga delimo z 2
- v nasprotnem primeru število pomnožimo s 3 in mu prištejemo 1

Pa še vedno nepreverjeni _Collatzovi domnevi_ bi nas opisani postopek moral za vsako pozitivno celo število pripeljati do enice.

Npr. če pričnemo s številom 7, dobimo zaporedje s 17 členi (štejemu tudi začetno 7):  
7 -> 22 -> 11 -> 34 -> 17 -> 52 -> 26 -> 13 -> 40 -> 20 -> 10 -> 5 -> 16 -> 8 -> 4 -> 2 -> 1

### Primer

**Vhod:**

```text
7
```

**Izhod:**

```text
17
```

### Rešitev

<details>
<summary><i>Program.java</i></summary>

```java
import java.util.Scanner;

class Program {
	public static void main(String[] args) {
		Scanner scn = new Scanner(System.in);

		// Preberemo vhod iz konzole
		int n = scn.nextInt();

		// Pripravimo stevec clenov zaporedja
		int stevec = 1;

		while (n != 1) {
			// Izracunamo naslednji clen zaporedja
			if (n % 2 == 0)
				n /= 2;
			else
				n = n * 3 + 1;

			// Pristejemo stevcu clenov
			stevec++;
		}

		// Izpisemo stevilo clenov zaporedja
		System.out.println(stevec);
	}
}
```
</details>

## 5. Collatzovo zaporedje II

Napišite program, ki prebere števili `a` in `b` ter izpiše, katero število med `a` in vključno `b` tvori najdaljše Collatzovo zaporedje in kako dolgo je to zaporedje.

### Primer

**Vhod:**

```text
10 20
```

**Izhod:**

```text
18
21
```

Število 18 tvori zaporedje z 21 členi: 8, 9, 28, 14, 7, 22, 11, 34, 17, 52, 26, 13, 40, 20, 10, 5, 16, 8, 4, 2, 1.

### Namig

Za osnovo programa lahko vzamete rešitev prejšnje naloge, kjer so se naučili poiskati dolžino Collatzovega zaporedja.

### Rešitev

<details>
<summary><i>Program.java</i></summary>

```java
import java.util.Scanner;

class Program {
	public static void main(String[] args) {
		Scanner scn = new Scanner(System.in);

		// Preberemo vhod iz konzole
		int a = scn.nextInt();
		int b = scn.nextInt();

		// Pripravimo spremenljivke, kjer bomo hranili zacetno stevilo najvecjega
		// zaporedja
		// in njegovo dolzino
		int najZaporedje = 1;
		int najDolzina = 1;

		// Iteriramo cez vse kandidate (tj. stevila od a do b)
		for (int i = a; i <= b; i++) {
			// Pripravimo stevec clenov zaporedja
			int stevec = 1;

			// Pripravimo spremenljivko, ki bo sledila clenom zaporedja
			int n = i;

			while (n != 1) {
				// Izracunamo naslednji clen zaporedja
				if (n % 2 == 0)
					n /= 2;
				else
					n = n * 3 + 1;

				// Pristejemo stevcu clenov
				stevec++;
			}

			// Ce smo nasli novo najdaljse zaporedje, ga shranimo v za to namenjene
			// spremenljivke
			if (stevec > najDolzina) {
				najZaporedje = i;
				najDolzina = stevec;
			}
		}

		// Izpisemo zacetno stevilo najdaljsega zaporedja in dolzino le tega
		System.out.println(najZaporedje);
		System.out.println(najDolzina);
	}
}
```
</details>

## 6. Piramida

Napišite program, ki prebere pozitivno celo število `n`, nato pa nariše »piramido« zvezdic višine `n`, kot jo prikazujejo primeri v nadaljevanju.

### Primer

**Vhod:**

```text
4
```

**Izhod:**

```text
   *
  ***
 *****
*******
```

### Rešitev

<details>
<summary><i>Program.java</i></summary>

```java
import java.util.Scanner;

class Program {
	public static void main(String[] args) {
		Scanner scn = new Scanner(System.in);

		// Preberemo vhod iz konzole
		int n = scn.nextInt();

		// Iteriramo cez vse nivoje piramide
		for (int i = 0; i < n; i++) {
			// Izpisemo presledke na danem nivoju
			for (int j = 0; j < n - i - 1; j++)
				System.out.print(" ");
			// Izpisemo zvezdice na danem nivoju
			for (int j = 0; j < 2 * i + 1; j++)
				System.out.print("*");
			// Pomaknemo se v novo vrstico
			System.out.println();
		}
	}
}
```
</details>

## 7. Kleptomanka Anka

Kleptomanka Anka1 bi rada ukradla kolo, ki je zaščiteno s številčno ključavnico. Ključavnica ima tri številska mesta (a-b-c). Nekdo Anki prišepne, da je prva števka liha, druga večja od `m`, tretja pa deljiva z `d`.

Napišite program, ki prebere števili m in d ter izpiše vse možne kombinacije števk.  
Na koncu naj izpiše še število vseh kombinacij.

### Primer

**Vhod:**

```text
7 3
```

<details>
<summary><b>Izhod:</b></summary>

```text
1-8-0
1-8-3
1-8-6
1-8-9
1-9-0
1-9-3
1-9-6
1-9-9
3-8-0
3-8-3
3-8-6
3-8-9
3-9-0
3-9-3
3-9-6
3-9-9
5-8-0
5-8-3
5-8-6
5-8-9
5-9-0
5-9-3
5-9-6
5-9-9
7-8-0
7-8-3
7-8-6
7-8-9
7-9-0
7-9-3
7-9-6
7-9-9
9-8-0
9-8-3
9-8-6
9-8-9
9-9-0
9-9-3
9-9-6
9-9-9
40
```
</details>

### Rešitev

<details>
<summary><i>Program.java</i></summary>

```java
import java.util.Scanner;

class Program {
	public static void main(String[] args) {
		Scanner scn = new Scanner(System.in);

		// Preberemo vhod iz konzole
		int m = scn.nextInt();
		int d = scn.nextInt();

		// Pripravimo stevec kombinacij
		int stevec = 0;

		// Iteriramo cez vse lihe stevke, za prvo stevko kombinacije
		for (int a = 1; a < 10; a += 2) {
			// Iteriramo cez vse stevke vecje od m, za drugo stevko kombinacije
			for (int b = m + 1; b < 10; b++) {
				// Iteriramo cez vse stevke deljive z d, za tretjo stevko kombinacije
				for (int c = 0; c * d < 10; c++) {
					// Izpisemo kombinacijo in pristejemo stevec najdenih kombinacij
					System.out.println(a + "-" + b + "-" + c * d);
					stevec++;
				}
			}
		}

		// Izpisemo stevec najdenih kombinacij
		System.out.println(stevec);
	}
}
```
</details>

## 8. Klub anonimnih potrošnikov

Razpas trgovin je pripeljal do zasvojenosti z nakupovanjem. Ena od metod zdravljenja temelji na inteligentnih košaricah, ki sprejmejo največ deset artiklov; po tem se zaklenejo in jih lahko kupec le še odnese na blagajno. Prav tako se zaklenejo, če cena artiklov doseže (ali preseže) 100 evrov.

Napišite program, ki mu uporabnik vnaša cene in se neha izvajati, ko uporabnik vnese 0 (ne bo več kupoval) ALI ko je vnešenih deset števil ALI ko vsota cen doseže ali preseže 100 evrov.

### Primer

**Vhod:**

```text
Cena: 10
Cena: 5
Cena: 0
```

**Izhod:**

```text
Porabili boste 15 evrov za 2 stvari.
```

Pazi, kupec je za tretji izdelek vnesel nič, zato štejemo samo dva izdelka.

### Rešitev

<details>
<summary><i>Program.java</i></summary>

```java
import java.util.Scanner;

class Program {
	public static void main(String[] args) {
		Scanner scn = new Scanner(System.in);

		// Pripravimo spremeljivke za belezenje vnesenih podatkov
		int stIzdelkov = 0;
		int vsota = 0;

		// Podatke beremo dokler sta spodnja pogoja izpolnjena
		while (stIzdelkov < 10 && vsota < 100) {
			// Vprasamo uporabnika za ceno
			System.out.print("Cena: ");
			int cena = scn.nextInt();

			if (cena > 0) {
				// Ce je cena vecja od 0, jo pristejemo vsoti in inkrementiramo stevilo izdelkov
				vsota += cena;
				stIzdelkov++;
			} else {
				// Drugace prekinemo zanko
				break;
			}
		}

		// Na koncu izpisemo vsoto in stevilo izdelkov
		System.out.println("Porabili boste " + vsota + " evrov za " + stIzdelkov + " stvari.");
	}
}
```
</details>

## 9. Deljitelji

Napišite program, ki sprejme število in izpiše vse njegove deljitelje.

### Primer

**Vhod:**

```text
18
```

**Izhod:**

```text
1
2
3
6
9
18
```

### Rešitev

<details>
<summary><i>Program.java</i></summary>

```java
import java.util.Scanner;

class Program {
	public static void main(String[] args) {
		Scanner scn = new Scanner(System.in);
		
		// Preberemo vhod iz konzole
		int st = scn.nextInt();

		// Preverimo vsa stevila od 1 do vkljucno st/2
		// lahko bi preverili tudi do vkljucno st, a to ni potrebno - pomisli zakaj!
		for (int i = 1; i <= st / 2; i++) {
			// Ko najdemo deljitelj, ga izpisemo
			if (st % i == 0)
				System.out.println(i);
		}

		// Vsako stevilo je samo svoj deljitelj, zato izpisemo tudi stevilo samo
		System.out.println(st);
	}
}
```
</details>
