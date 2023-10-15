
> **Programmieren für Naturwissenschaften FS 2023**
> Gruppe: Sofia Kessler, Florian Mohaupt, Lukas Batschelet

## Aufgabe 1: Kreisberechnung

> [!Aufgabe]
> Schreiben Sie eine Funktion, welche über einen formalen Parameter verfügt, welcher dem Radius eines Kreises entspricht. Die Funktion soll die Fläche und den Umfang des Kreises berechnen und die Berechnungen dann mit Hilfe des Schlüsselworts `return` zurückgeben. Rufen Sie die Funktion danach 3-mal mit je einem anderen tatsächlichen Parameter auf und speichern Sie die Rückgabewerte der Funktion in zwei Listen, um diese dann mit Hilfe der Funktion `print` auszugeben.
>
> **Tipp:** Wenn Sie nicht wissen, wie Sie in einer Funktion mehrere Werte zurückgeben können, betrachten Sie Beispiel 76 im Skript auf Seite 102

### Mögliche Lösung

```python
import math

def circle(rad=0):
    area = math.pow(rad, 2) * math.pi
    circumference = rad * 2 * math.pi
    return area, circumference

radien = []
flaechen = []
umfange = []

loop = "y"
while loop == "y":
    rad = float(input("Geben Sie den Radius eines Kreises ein: "))
    area, circumference = circle(rad)
    radien.append(round(rad, 2))
    flaechen.append(round(area, 2))
    umfange.append(round(circumference, 2))
    print("Radius:", rad)
    print("Fläche: ", area)
    print("Umfang: ", circumference)
    loop = input("Wollen Sie noch einen weiteren Kreis berechnen? (y/n)")

print("Radien: ", radien)
print("Flächen: ", flaechen)
print("Umfänge: ", umfange)

```

<div style="page-break-after: always;"></div>

## Aufgabe 2: Funktionsparameter

> [!Aufgabe]
> Schreiben Sie eine Funktion `greet`, welche bis zu drei Parameter akzeptiert, jedoch mindestens einen Parameter benötigt, nämlich den Namen einer Person. Unten finden Sie einige Beispiele, welche Ausgaben die Funktion generieren sollten. Passen Sie Ihre Funktion so an, dass die Beispiele in Tabelle 1 funktionieren. Falls Sie Hilfe brauchen, schauen Sie sich Beispiel 73 auf Seite 94 im Skript an
>
> | Funktionsaufruf                        | Ausgabe                                                              |
> | -------------------------------------- | -------------------------------------------------------------------- |
> | `greet("Monika")`                      | `Hallo Monika!`<br>`Guten Morgen!`<br>`Es ist 20 Grad draussen.`       |
> | `greet("Sepp", "Wie geht's denn so?")` | `Hallo Sepp!`<br>`Wie geht's denn so?`<br>`Es ist 20 Grad draussen.` |
> | `greet("Hans", temp=10)`               | `Hallo Hans!`<br>`Guten Morgen!`<br>`Es ist 10 Grad draussen.`       |
>
> Tabelle 1: Ihre Funktion sollte dieselben Ausgaben generieren, wie in dieser Tabelle dargestellt.

### Mögliche Lösung

```python
def greetings(name, gruss="Guten Morgen!", temp=20):
    print("Hallo ", name, "!\n", gruss, "\nEs ist draussen", temp, "Grad warm.")
``` 

<div style="page-break-after: always;"></div>

## Aufgabe 3: Funktionen auslagern

> [!Aufgabe]
> Betrachten Sie das untenstehendes Programm. Sie werden bemerken, dass das Programm verschiedene Verantwortungen übernimmt. Ihre Aufgabe ist es, die einzelnen Verantwortungen zu identifizieren und für jede Verantwortung je eine Funktion zu definieren und den Code entsprechend auszulagern. Rufen Sie danach Ihre Funktionen in der richtigen Reihenfolge auf – verwenden Sie wo sinnvoll Parameter und Rückgaben.
> 
> ```python
> ages = []
> done = False
> 
> while not done:
> 	user_input = int(input("Alter eingeben: (-1 zum Beenden): "))
> 	if user_input == -1:
> 		done = True
> 	else:
> 		ages.append(user_input)
> 
> print("Alle Alter aufsteigend sortiert:")
> ages.sort()
> for i in range(len(ages)):
> 	print("Alter von Student", i, ages[i])
> 
> import statistics
> print("Mittelwert der Alter: ", round(statistics.mean(ages), 2))
> ```

### Mögliche Lösung

```python
# S9A3_main.py
from S9A3_ages import age_list, sort_and_print, mean_and_print

ages = age_list()
sort_and_print(ages)
mean_and_print(ages)
```


```python
# S9A3_ages.py
import statistics

def age_list():
    ages = []
    done = False
    while not done:
        user_input = int(input("Alter eingeben (-1 zum Beenden): "))
        if user_input == -1:
            done = True
        else:
            ages.append(user_input)
    return ages

def sort_and_print(list):
    print("Alle Alter aufsteigend sortiert:")
    list.sort()
    for i in range(len(list)):
        print("Alter von Student:in", i + 1, list[i])

def mean_and_print(list1):
    mean = statistics.mean(list1)
    print("Durchschnittsalter:", round(mean, 2))
```
