
Lukas Batschelet (16-499-733)

## Theorieaufgaben

### 1. Bezeichner

> [!Aufgabe]
> Finden Sie passende Bezeichner für...
> - eine Java Klasse, die eine Prüfung repräsentieren soll.
> - die erreichten Punkte in einer Prüfung.
> - eine Methode, welche den Durchschnittswert aller Prüfungen berechnet.
> - die maximale Punktzahl, die in einer Prüfung erreicht werden kann.

#### Lösung

```java
1. public class Exam {}
2. int points
3. meanPoints()
4. final int MAX_POINTS
```

  
### 2. Variablen und Eigenschaften

> [!Aufgabe]
> Finden Sie für die Klasse `Flight` mindestens drei Variablen (Eigenschaften) und drei Methoden (Verhalten/Funktionen), die in den Klassen modelliert werden könnten.

#### Mögliche Lösung

##### 2.1 Variablen

1. `altitude`
2. `cargoWeight`
3. `fuelRemaining`

##### 2.2 Methoden

1. `bookSeat()`
2. `cancelFlight()`
3. `readFuelLevel()`


### 3. Zitat

> [!Aufgabe]
> Schreiben Sie eine einzige `println` Anweisung, die die folgende Zeichenkette als Ausgabe generiert:
>  
> ```
> "Mein Name ist Winston Wolfe.  
> Ich löse Probleme!", stellte er sich vor.
> ```

#### Lösung

```java
System.out.println("\"Mein Name ist Winston Wolfe. \n" +
	"Ich löse Probleme!\", stellte er sich vor.");
```

<div style="page-break-after: always;"></div>

### 4. Rechnung

> [!Aufgabe]
> Welchen Wert enthält die Variable `result`, nachdem folgende Anweisungen durchgeführt worden sind?
>
> ```java  
> int result = 25;  
> result = result + 5;  
> result = result / 7;  
> result = result * 3;  
> ```

#### Lösung

```java
int result = 25;
result = result + 5; //30
result = result / 7; //4
result = result * 3; //12
```


### 5. Rechnung

> [!Aufgabe]
> Welchen Wert enthält die Variable `result`, nachdem folgende Anweisungen durchgeführt worden sind?
> 
> ```java  
> int result = 15, total = 100, min = 15, num = 10;  
> result /= (total - min) % num;  
> ```

#### Lösung

```java
int result = 15, total = 100, min = 15, num = 10;
result /= (total – min) % num;
result = result / ((total – min) % num;
3 = 15 / (( 100 - 15) % 10;
```


### 6. Operationen

> [!Aufgabe]
> Gegeben seien folgende Deklarationen:
>
> ```java  
> int result1, num1 = 27, num2 = 5;  
> double result2, num3 = 12.0;  
> ```
>
> Welches Resultat wird jeweils durch folgende Anweisungen gespeichert?
>
> 1. `result1 = num1 / num2;`  
> 2. `result2 = num1 / num2;`  
> 3. `result2 = num3 / num2;`  
> 4. `result1 = (int) num3 / num2;`  
> 5. `result2 = (double) num1 / num2;`

#### Lösung

```java
int result1, num1 = 27, num2 =5;
double result2, num3 = 12.0;
a. result1 = num1 / num2; //5.0
b. result2 = num1 / num2; //5.4
c. result2 = num3 / num2; //2.4
d. result1 = (int) num3 / num2; //2
e. result2 = (double) num1 / num2; //5.4
```

<div style="page-break-after: always;"></div>

### 7. Boolsche Operationen

> [!Aufgabe]
> Gegeben seien folgende Deklarationen:
>
> ```java  
> int val1 = 15, val2 = 20;  
> boolean ok = false;  
> ```
>
> Was ist der Wert der folgenden Booleschen Ausdrücke?
>
> 1. `val1 <= val2`  
> 2. `(val1 + 5) >= val2`  
> 3. `val1 < val2 / 2`  
> 4. `val1 != val2`  
> 5. `!(val1 == val2)`  
> 6. `(val1 < val2) || ok`  
> 7. `(val1 > val2) || ok`  
> 8. `(val1 < val2) && !ok`  
> 9. `ok || !ok`

#### Lösung

```java
int val1 = 15, val2 = 20;
Boolean ok = false;
a. true
b. true
c. false
d. true
e. true
f. true
g. false
h. true
i. true
```

<div style="page-break-after: always;"></div>

## Implementationsaufgaben

### 1. Einfache Ausgabe - `WinterIsComing.java`

> [!Aufgabe]
> Schreiben Sie ein Programm, welches den Satz "Winter is coming" ausgibt (erste Version: auf einer Zeile; zweite Version: jedes Wort auf einer separaten Zeile).

#### Lösung

```java
public class WinterIsComing {
    public static void main(String[] args) {
		System.out.println("\"Winter is coming\"");
		System.out.println("\"Winter \n" +
				"is \n" +
				"coming\"");
	}
}
```

### 2. Einfache Berechnungen - `Quotient.java`

> [!Aufgabe]
> Schreiben Sie ein Programm, das vom Benutzer die Eingabe von zwei ganzzahligen Werten `a` und `b` fordert. Ihr Programm soll den Quotienten $\frac{a^2}{b}$ sowohl als Gleitkommazahl (d.h. ungerundet) als auch als ganze Zahl mit Rest berechnen und beide Ergebnisse am Bildschirm ausgeben. Testen Sie Ihr Programm mit beliebigen Zahlen.
> 
> Beobachten Sie insbesondere das Programmverhalten bei Eingabe der Zahl `0` als Divisor und versuchen Sie diesen Laufzeitfehler abzufangen.

#### Mögliche Lösung

```java
import java.util.Scanner;

public class Quotient {
    public static void main(String[] args) {

        System.out.println("Dieses Programm berechnet den Quotienten zweier Zahlen \"a\" und \"b\".");
        
        Scanner scan = new Scanner(System.in);
        System.out.println("Geben Sie den Teil \"a\" ein:");
        double var1 = scan.nextDouble();
        
        System.out.println("Geben Sie den Teil \"b\" ein:");
        double var2 = scan.nextDouble();
        
        if (var2 != 0) { //Wert 0 führt zu divide by zero
            double quotientDouble = (var1 * var1) / var2;
            // int quotientInt = (int) var1 * (int) var1) / (int) var2;
            int quotientInt = (int) quotientDouble;
            System.out.println("_________________________________________\n" + 
                "Der Quotient Ihrer Zahlen: \t" + quotientDouble + 
                "\nUnd als \"int\":\t \t \t" + quotientInt);
        } else { 
            System.out.println("Geben Sie nicht 0 ein!");
        }
        scan.close();
    }
}
```

<div style="page-break-after: always;"></div>

### 3. Benutzerinteraktion - `HumanThermometer.java`

> [!Aufgabe]
> Schreiben Sie ein Programm, das vom Benutzer die Eingabe einer Temperatur `t` fordert. Die Ausgabe Ihres Programmes definiert sich danach folgendermassen:  
> $$
> Ausgabe =  
> \begin{cases}
> "Kalt", & \text{wenn } t < 15 \\
> "Angenehm", & \text{wenn } 15 \leq t < 24 \\
> "Warm", & \text{wenn } t \geq 24
> \end{cases}
> $$
> Hinweis: Verwenden Sie Konstanten für beide Temperaturgrenzen.

#### Mögliche Lösung

```java
import java.util.Scanner;

public class HumanThermometer {
    public static void main(String[] args) {
		final int LOWER_BOUND = 15;
		final int UPPER_BOUND = 24;
		
		Scanner scan = new Scanner(System.in);
		System.out.println("Die aktuelle Temperatur: ");
		int temperature = scan.nextInt();
		
		if (temperature < LOWER_BOUND) {
			System.out.println("Es ist kalt");
		} 
		else if ((LOWER_BOUND <= temperature) && (temperature <= UPPER_BOUND)) {
			System.out.println("Es ist angenehm");
		} 
		else
			System.out.println("Es ist warm");
		
		scan.close();
	}
}
```

