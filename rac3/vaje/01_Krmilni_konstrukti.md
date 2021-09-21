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
