
> **Programmieren für Naturwissenschaften FS 2023**
> Gruppe: Sofia Kessler, Florian Mohaupt, Lukas Batschelet

## Aufgabe 1: Fakultät einer Zahl

> [!Aufgabe]
> Schreiben Sie zwei Varianten eines Programmes, welche beide die Fakultät *n!* einer nichtnegativen ganzen Zahl *n* berechnen und ausgeben. Die beiden Programme sollten nach dem gleichen Prinzip funktionieren und sich nur darin unterscheiden, dass eines eine `for`-Schleife und das andere eine `while`-Schleife verwendet. Die Zahl *n* soll vom Benutzer eingelesen werden
>
> **Hinweis:** Die Fakultät einer natürlichen Zahl ist das Produkt aller natürlichen Zahlen (ohne Null) kleiner und gleich dieser Zahl. Die Fakultät von Null ist als 1 definiert
> $$ 
> \begin{align}
> n! &:= n \cdot (n-1) \cdot (n-2) \cdot \ldots \cdot 2 \cdot 1 \\
> 0! &:= 1
> \end{align}
> $$
> Beispiel: 
> $$ 5! = 5 \cdot 4 \cdot 3 \cdot 2 \cdot 1 = 120 $$
> Die Ausgabe Ihres Skripts sollte in beiden Fällen gleich aussehen, beispielsweise wie folgt:
>
> ```
> Bitte geben Sie eine nichtnegative ganze Zahl ein: 6
> Die Fakultät dieser Zahl: 720
> ```

### Mögliche Lösung `for`-Schleife

```python
number = int(input("Geben Sie eine natürliche Zahl ein: "))
produkt = 1
for i in range(1, number+1):
    produkt *= i
  
print("Fakultät dieser Zahl: ", produkt)
```

### Mögliche Lösung `while`-Schleife

```python
number = int(input("Geben Sie eine eine Natürliche Zahl ein: "))
produkt = 1
while number > 0:
    produkt *= number
    number -= 1
print("Fakultät dieser Zahl: ", produkt)
```

<div style="page-break-after: always;"></div>

## Aufgabe 2: Durchschnittsalter

> [!Aufgabe]
> Schreiben Sie ein Programm, welches das Durchschnittsalter aller Studierenden einer Vorlesung berechnen kann. Die Anzahl der Studierenden ist dabei nicht bekannt. Ihr Programm soll so lange nach dem Alter der Studierenden fragen, bis eine gewisse Eingabe erfolgt, welche die Abfrage beendet. Danach soll das Durchschnittsalter der Studierenden auf zwei Nachkommastellen gerundet ausgegeben werden.
>
> **Hinweise:**
> 1. Die Eingabe, welche die Abfrage beenden soll, muss eindeutig sein, und sich klar von den anderen Eingaben (dem Alter der Studierenden) unterscheiden.
> 2. Lagern Sie die Berechnung des Durchschnittsalters in eine weitere Funktion aus.
>
> Die Ausgabe Ihres Skripts könnte wie folgt aussehen:
>
> ```
> Geben Sie das Alter der Studenten jeweils auf einer neuen Zeile ein. Um
> die Eingabe der Daten zu stoppen und das Durchschnittsalter zu berechnen,
> geben Sie 0 ein.
>
> Alter: 23
> Alter: 18
> Alter: 22
> Alter: 21
> Alter: 0
> Durchschnittsalter: 21.00
> ```

### Mögliche Lösung

```python
another = "y"
while another == "y" or another == "Y":
    alter_summe = 0
    count = 0
    print("Dieses Programm rechnet ihnen das Durchschnittsalter einer Gruppe aus. Geben sie das alter der Personen einzeln ein. Beenden können Sie das Programm mit der Eingabe 0")
    alter_neu = int(input("Geben Sie das Alter eines Studierenden oder einer Studierenden ein: "))
    while alter_neu > 0:
        count += 1
        alter_summe += alter_neu
        alter_neu = int(input("Geben Sie das Alter eines Studierenden oder einer Studierenden ein: "))
        
    alter_durchscnitt = alter_summe / count

    print("Durchschnittsalter: ", round(alter_durchscnitt, 2))
    another = input("Möchten Sie ein weiteres Durchschnittsalter berechnen? (y/n)")

```

<div style="page-break-after: always;"></div>

## Aufgabe 3: km/h zu mph

> [!Aufgabe]
> Schreiben Sie ein Programm, welches die Werte `60`, `70`, ..., `120` von km/h in mph umrechnet und ausgibt (`km/h / 1.609 = mph`). Verwenden Sie in Ihrem Programm eine `for`-Schleife. Die Ausgabe Ihres Skripts könnte wie folgt aussehen:
>
> ```
> 60 kmh = 37.3 mph
> 70 kmh = 43.5 mph
> 80 kmh = 49.7 mph
> 90 kmh = 55.9 mph
> 100 kmh = 62.1 mph
> 110 kmh = 68.4 mph
> 120 kmh = 74.6 mph
> ```

### Mögliche Lösung

```python
for val_m in range(60, 121, 10):
    val_i = val_m / 1.609
    print(val_m, "km/h = ", round(val_i, 2), "mph" )
```
