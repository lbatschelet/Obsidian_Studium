## Aufgaben zu Kapitel 7

Was ist die Ausgabe des folgenden Code-Fragments?

```java
int[] values = {1, 4, -8, 9, 10, 101, 17, 1};
System.out.println(values[1]);
System.out.println(values[2] + values[5]);
System.out.println(values[2 + 5]);
System.out.println(values.length);
System.out.println(values[values.length - 2]);
```

```text
4
93
1
8
17
```


Gegeben sei ein beliebiges int[] values. Schreiben Sie je ein Code-Fragment, das ...
- ... jedem Element in values den entsprechenden Index zuweist: [0, 1, 2, ...]
- ... alle Werte in values um 1 erhöht.
- ... dem i-ten Wert (i>0) in values die Summe aller vorangegangen Elemente zuweist: values[i] = values[0] + values [1] + ... + values[i-1]. Das 0-te Element setzen Sie auf 1.

```java
for (i : values) {
	values[i] = i;
}
```

```java
for (i : values) {
	values[i]++;
}
```

```java
values[0] = 1;

for (i = 1; i < values; i++) {
	int sum = 0;
	for (int j = 0; j < i; j++) {
		sum += values[j];
	}
	values[i] = sum;
}
```

Schreiben Sie eine Service Methode `minFinder`, welche mindestens einen und maximal beliebig viele `double` Werte als Parameter entgegennehmen kann und danach das Minimum aller Werte zurückgibt.

```java
public double minFinder(double min, double ... others) {
	for (double val : others){
		if (others[val] < min)
			min = others[val];
	}
	return min;
}
```

Schreiben Sie eine Support Methode `swap`, welche ein `int[]` und zwei Indizes `i` und `j` als Parameter entgegennimmt. Tauschen Sie in der Methode das `i`-te und das `j`-te Element im Array. Überprüfen Sie, ob die Indizes gültig sind! Lösung ohne temporäre Variable?

```java
private void swap(int[] list, int i, int j) {
	if (Math.max(i, j) > list.length() && Math.min(i, j) >= 0)
		System.out.println("Ungültige Eingabe");
	else {
		int temp = list[i];
		list[i] = list[j];
		list[j] = temp;
	}
}
```

```java
private void swap(int[] list, int i, int j) {
	if (Math.max(i, j) > list.length() && Math.min(i, j) >= 0)
		System.out.println("Ungültige Eingabe");
	else {
		list[i] = list[i] + list[j];
		list[j] = list[i] - list[j];
		list[i] = list[i] - list[j];
	}
}
```

Schreiben Sie eine Service Methode `span`, welche ein `int[][]` als Parameter entgegennimmt und die maximale Wertespanne der Werte zurückgibt (Maximum - Minimum)

```
public int span(int[][] table) {
	int min = Integer.MAX_VALUE;
	int max = Integer.MIN_VALUE;
	for (int i = 0; i < table.length(); i++){
		for (int j = 0; j < table[i].length(); j++) {
			min = Math.min(min, table[i][j]);
			max = Math.max(max, table[i][j]);
		}
	}
	return max - min;
}
```

Ergänzen Sie das folgende Programm, das vom Benutzer einen Satz einliest. Danach soll analysiert werden, wie oft die 26 Buchstaben des Alphabets im Satz vorkommen (Gross- und Kleinschreibung soll dabei ignoriert werden). Sonderzeichen (z.B. Leerschläge) sollen gesondert gezählt werden.

Tipps:

- Weisen Sie jedem Buchstaben einem Zähler im Array letterCount zu (indem Sie an Position 0 des Arrays z.B. die Anzahl der Buchstabens 'A' und 'a' zählen, an Position 1 zählen Sie die Buchstaben 'B' und 'b' und so weiter.
- Verwenden Sie den Unicode Wert des aktuellen Zeichens, um herauszufinden, welcher Zähler im Array erhöht werden soll. Z.B. hat der Buchstabe 'E' den Unicode 69.
- Wenn man zwei char addiert oder subtrahiert, wird der entsprechende Unicode Wert verrechnet: 'E' - 'A' = 4

```
Scanner scan = new Scanner (System.in);
System.out.println ("Geben Sie einen Satz ein:");
String line = scan.nextLine();

final int NUMCHARS = 26;
int[] letterCount = new int[NUMCHARS];

char current; // aktuelles Zeichen
int other = 0; // Zähler für Sonderzeichen

line = line.toLowerCase();
for (int i = 0; i < line.length(); i++) {
	current = line.charAt(i);
	if (current >= 'a' && current <= 'z') {
		letterCount[current - 'a']++;
	} else {
		other++;
	}
}
```