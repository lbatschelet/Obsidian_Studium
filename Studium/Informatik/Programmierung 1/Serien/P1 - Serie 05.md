Lukas Batschelet (16-499-733)

> [!Bemerkung]
> Organisiert die Aufgaben in Packages. Sprich ein Package `game` für Aufgabe 1 und ein Package `matrizen`für Aufgabe 2.

## Implementationsaufgaben

### Vier Gewinnt

> [!Aufgabe]
> 1. Sie sollen ein “Vier gewinnt“ Spiel programmieren, bei dem man in der Konsole gegen eine zweite Person spielen kann. Laden Sie von ILIAS die Dateien `VierGewinnt.java`, `Player.java` und `Token.java` herunter. Die Klasse `VierGewinnt` enthält bereits Methoden `play()` (definiert den Spielablauf), `main` (startet das Spiel) und `displayField()` (graphische Darstellung des Spielfelds):
>    ```
>    1
>    Player X choose a column between 1 and 7: 2
>    +---+---+---+---+---+---+---+
>    |   |   |   |   |   |   |   |
>    +---+---+---+---+---+---+---+
>    |   |   |   |   |   |   |   |
>    +---+---+---+---+---+---+---+
>    | X |   |   |   |   |   |   |
>    +---+---+---+---+---+---+---+
>    | O | X | O |   |   |   |   |
>    +---+---+---+---+---+---+---+
>    | X | O | X |   |   |   | X |
>    +---+---+---+---+---+---+---+
>    | O | O | O | X | X |   | O |
>    +---+---+---+---+---+---+---+
>      1   2   3   4   5   6   7
>    Player X wins!
>    ```
> 2. Um das Spiel zum Laufen zu bekommen, müssen Sie in der Klasse `VierGewinnt` die folgenden Methoden implementieren (die anderen gegebenen Methoden dürfen Sie nicht verändern):
> 	1. `insertToken`: Der übergebene Stein (Token-Objekt) soll in die gewählte Spalte (column) des Spielfelds (Array[][] board) gefüllt werden. Falls eine nicht existierende oder bereits bis oben gefüllte Spalte gewählt wurde, soll das Programm mit einer Fehlermeldung abbrechen. Verwenden Sie dazu `System.exit(1)`.
> 	2. `isBoardFull`: gibt genau dann true zurück, wenn alle Felder durch einen Stein besetzt sind.
> 	3. `checkVierGewinnt`: überprüft – ausgehend vom durch col und row gegebenen Feld – ob es in einer der vier Richtungen (d.h. –,|,/,\\) mindestens vier gleiche Steine gibt. In diesem Fall wird true zurückgegeben, andernfalls false. Tipp: Schreiben Sie für jede der vier Richtungen eine Hilfsmethode.


### Rechnen mit Matrizen

> [!Aufgabe]
>    *Anmerkungen:*
>    - Diese Aufgabe erfordert den Gebrauch statischer Methoden und der Klasse `Scanner` zum Einlesen von Daten aus einer Datei. Beides wird nächste Woche in der Vorlesung eingeführt. Wir empfehlen, die folgenden Teilaufgaben erst nach dem Studium von Kapitel 8 zu lösen!
>    - In den folgenden Teilaufgaben werden die Matrizen \(A\), \(B\), \(C\) als 2-dimensionale Arrays dargestellt (z.B. `int[][] A = new int[m][n];`).
>
> 1. Schreiben Sie in einer Klasse `MatrixOperations` eine statische Methode `readMatrix`, welche die Daten einer Matrix aus einer Datei einliest. Eine Matrix-Datei sei dabei folgendermassen formatiert:
>        ```
>        1 2 3
>        4 5 6
>        ```
>        Speichern Sie die eingelesenen Daten in einem 2-dimensionalen Array.
>
> 2. Schreiben Sie in der Klasse `MatrixOperations` eine statische Methode `transpose`^[https://de.wikipedia.org/wiki/Transponierte_Matrix], welche eine $n \times n$ Matrix $A$ als Parameter erhält und $A^T$ (die transponierte Matrix $A$ zurückgibt. Falls die übergebene Matrix nicht quadratisch sein sollte, erzeugen Sie eine Fehlermeldung und geben `null` zurück. Beim Transponieren einer Matrix spiegelt man einen Matrixeintrag $a_{ij}$ an der Diagonalen von $A$. Einfach gesagt, aus $a_{ij}$ wird $a_{ji}$.
>    $$
>        A =
>        \begin{pmatrix}
>        a_{00} & a_{01} & a_{02} \\
>        a_{10} & a_{11} & a_{12} \\
>        a_{20} & a_{21} & a_{22}
>        \end{pmatrix}\ und\ A^T =
>        \begin{pmatrix}
>        a_{00} & a_{10} & a_{20} \\
>        a_{01} & a_{11} & a_{21} \\
>        a_{02} & a_{12} & a_{22}
>        \end{pmatrix}
>  $$
>  
>  Ihre Methode sollte alle möglichen Werte von $n$ berücksichtigen.
>
> 3. Schreiben Sie in der Klasse `MatrixOperations` eine statische Methode `product`^[https://de.wikipedia.org/wiki/Matrizenmultiplikation], welche eine $n \times m$ Matrix $A$ und eine $m \times l$ Matrix $B$ als Parameter entgegennimmt und das Produkt $C = AB$ zurückgibt. Die Dimension von $C$ ist $n \times l$ und die Einträge $c_{ij}$ berechnen sich wie folgt:
>  
>  $$
> c_{ij} = \sum_{k=0}^{n-1} a_{ik}b_{kj}
> $$
> 
> Ihre Methode sollte alle möglichen Werte von $m$, $n$ und $l$ berücksichtigen. Falls die Anzahl Spalten von $A$ nicht mit der Anzahl Zeilen von $B$ übereinstimmen sollte, erzeugen Sie eine Fehlermeldung und geben Sie `null` zurück.
> 
> **Beispielechung**:
> 
> $$
> Input:\ A =
>        \begin{pmatrix}
>        1 & 2 \\
>        3 & 4 \\
>        5 & 6
>        \end{pmatrix}, B =
>        \begin{pmatrix}
>        1 & 2 & 3 \\
>        4 & 5 & 6 \\
>        \end{pmatrix} \\
>        \newline
>        Output: C =
>        \begin{pmatrix}
>        9 & 12 & 15 \\
>        19 & 26 & 33 \\
>        29 & 40 & 51
>        \end{pmatrix}
> $$
>
>    4. Erstellen Sie eine Klasse `MatrixTest.java` in der Sie die Methoden `readMatrix`, `transpose` und `product` mit geeigneten Beispielen testen. Achten Sie darauf bei der Methode `transpose` und `product` auch den Fehlerfall zu testen.
