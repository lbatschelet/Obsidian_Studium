## Aufgaben zu Kapitel 6

### Welche Ausgabe erzeugt das folgende Fragment für die drei Fälle:
- `int num1 = 9, num2 = 10;`
- `int num1 = 11, num2 = 10;`
- `int num1 = 13, num2 = 10;`

```java
if (num1 < num2)
	System.out.println("rot");
else
	if ((num1 - 2) < num2)
		System.out.println("blau");
	else
		System.out.println("weiss");
System.out.println("gelb");
```

```text
rot
gelb

blau
gelb

weiss
gelb

```

### Übersetzen Sie in eine switch-Anweisung:

```java
if (num == 1)
	c = 'A';
else
	if (num == 2)
		c = 'B';
	else
		if (num == 3)
			c = 'C';
		else
			c = 'Z';
```

```java
switch (num) {
	1 : c = 'A'; break;
	2 : c = 'B'; break;
	3 : c = 'C'; break;
	default : z = 'Z'; break;
}
```

### Übersetzen in einen Conditional
```java
System.out.println((val <= 100 ? "nicht " : "") + "grösser als 100.");
```

### `do`-loops

```java
int low = 0, high = 5;
do {
	low++;
	System.out.println(low);
} while (low < high);
```

```text
1
2
3
4
5
```

```java
int low = 5, high = 5;
do {
	System.out.println(low);
	low++;
} while (low < high);
```

```text
5
```

### Welche Ausgaben erzeugen folgende Schleifen?

```java
int max = 6;
for (int i = 0; i < max; i++)
	System.out.println(max + i);
```

```text
6
7
8
9
10
11
```

```java
int val = 0;
int num;
for (num = 10; num <= 40; num+=10)
	val += num;
System.out.println(num);
System.out.println(val);
```

```text
50
100
```

```java
for (int i = 0; i <= 3; i++) {
	for (int j = i + 1; j > 0; j--)
		System.out.print(i * j + " ");
	System.out.println();
}
```

```text
0
2 1
6 4 2
12 9 6 3
```

### Machen Sie die Klasse `Box`generisch

```java
public class Box {

	private String content;
	
	public Box(String content) {
		this.content = content;
	}
	
	public String getContent() {
		return this.content;
	}
}
```


```java
public class Box<T> {

	private T content;
	
	public Box(T content) {
		this.content = content;
	}
	
	public T getContent() {
		return this.content;
	}
}
```

- Instanziieren Sie eine Liste boxes, welche `Box<String>` Objekte aufnehmen kann.

```java
ArrayList<Box<String>> boxes = new ArrayList<Box<String>>;

for (Box<String> b :boxes)
	System.out.println(b.getContent())
```

### Ergänzen Sie die Klasse `Pasta` mit einer Methode `equals` und einer Methode `compareTo`.

```java
public class Pasta {

	private String name;
	private double price;

	public Pasta(String name, double price) {
		this.name = name;
		this.price = price;
}
```

```java
public class Pasta {

	private String name;
	private double price;

	public Pasta(String name, double price) {
		this.name = name;
		this.price = price;

	public boolean equals(Pasta other) {
	return (this.name.equals(other.name));
	}

	public int compareTo(Pasta other) {
	if (this.price == other.price)
		return 0;
	else if (this.price < other.price)
			return 1;
		else
			return -1;
}
```



