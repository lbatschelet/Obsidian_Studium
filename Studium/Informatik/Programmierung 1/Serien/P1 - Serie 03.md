# Implementationsaufgaben

## Aufgabe 1: `Thermometer`-Klasse

> [!Aufgabe]
> Programmieren Sie eine Klasse `Thermometer`, welche einen einfachen Fieberthermometer modelliert. Die Klasse soll eine Temperatur in Celsius als einzige Instanzvariable speichern. Der Konstruktor soll diese Instanzvariable standardmässig auf 37.0 Grad setzen. Schreiben Sie eine Methode `increase`, welche die Temperatur um 0.1 Grad erhöht und einen Getter für die Temperatur. Zudem definieren Sie eine Methode `reset`, welche die Temperatur wieder auf 37.0 zurücksetzt.
> 
> Schreiben Sie eine zweite Klasse `ThermometerTest`, in der Sie zwei Objekte vom Typ `Thermometer` instanziieren und deren Methoden ausführlich testen.

### Mögliche Lösung

#### Klasse `Thermometer`

```java
public class Thermometer {
    
    private double temperature;

    public Thermometer() {
        this.temperature = 37.0;
    }

    public void increase() {
        this.temperature += 0.1;
    }

    public double getTemperature() {
        return this.temperature;
    }

    public void reset() {
        this.temperature = 37.0;
    }
}
```

#### Klasse `ThermometerTest`

```java
public class ThermometerTest {
        
        public static void main(String[] args) {
            Thermometer thermometer1 = new Thermometer();
            Thermometer thermometer2 = new Thermometer();
            System.out.println(thermometer1.getTemperature());
            System.out.println(thermometer2.getTemperature());
            thermometer1.increase();
            System.out.println(thermometer1.getTemperature());
            System.out.println(thermometer2.getTemperature());
            
            for (int i = 0; i < 10; i++) {
                thermometer2.increase();
            }
            System.out.println(thermometer1.getTemperature());
            System.out.println(thermometer2.getTemperature());
            thermometer1.reset();
            thermometer2.reset();
            System.out.println(thermometer1.getTemperature());
            System.out.println(thermometer2.getTemperature());
        }
}
```

## Aufgabe 2: `Car`-Klasse

> [!Aufgabe]
> Programmieren Sie eine Klasse `Car`, welche die Marke, das Modell und den Jahrgang des Fahrzeuges modelliert. Der Konstruktor soll diese drei Instanzvariablen gemäss Parameterübergabe initialisieren – zudem schreiben Sie Getter und Setter für alle Instanzvariablen und eine `toString` Methode für eine einzeilige Repräsentation von `Car` Objekten. Schliesslich definieren Sie eine Methode `isAntique`, welche einen boolean zurückgibt, der anzeigt ob das Auto aktuell älter ist als 45 Jahre.
> 
> In einer zweiten Klasse `Garage` instanziieren Sie drei `Car` Objekte und testen alle programmierten Methoden.

### Mögliche Lösung

#### Klasse `Car`

```java
import java.time.LocalDate;

public class Car {
    
    private String brand;
    private String model;
    private int year;
    private boolean isAntique;
    private final int ANTIQUE_AGE = 45;

    public Car(String brand, String model, int year) {
        this.brand = brand;
        this.model = model;
        this.year = year;
        this.isAntique = checkIfAntique();
    }

    public String getBrand() {
        return this.brand;
    }

    public String getModel() {
        return this.model;
    }

    public int getYear() {
        return this.year;
    }

    public boolean getIsAntique() {
        return this.isAntique;
    }

    public void setBrand(String brand) {
        this.brand = brand;
    }

    public void setModel(String model) {
        this.model= model;
    }

    public void setYear(int year) {
        this.year = year;
        this.isAntique = checkIfAntique();
    }

    private boolean checkIfAntique() {
        int currentYear = LocalDate.now().getYear();
        if (currentYear - this.year > ANTIQUE_AGE) {
            return true;
        } else {
            return false;
        }
    }

    public boolean isAntique() {
        return this.isAntique;
    }

    public String toString() {
        return this.brand + " " + this.model + " " + this.year + " Is Antique: " + this.isAntique;
    }
}
```

#### Klasse `Garage`

```java
public class Garage {
        
        public static void main(String[] args) {
            Car car1 = new Car("BMW", "M3", 1900);
            Car car2 = new Car("Mercedes", "C63", 2010);
            Car car3 = new Car("Audi", "RS6", 2015);
            System.out.println("Car1 " + car1);
            System.out.println("Car2 " + car2);
            System.out.println("Car3 " + car3);

            car1.setYear(2000);
            System.out.println("Set car1 year to 2000");
            System.out.println("Car1: " + car1);

            car2.setBrand("Mercedes-Benz");
            System.out.println("Set car2 brand to Mercedes-Benz");
            System.out.println("Car2: " + car2);

            car3.setModel("RS7");
            System.out.println("Set car3 model to RS7");
            System.out.println("Car3: " + car3);

            car1.setYear(1984);
            System.out.println("Set car1 year to 1984");
            System.out.println("Car1: " + car1.getYear());
            System.out.println("Car1: " + car1.isAntique());

            car2.setBrand("Mercedes");
            System.out.println("Set car2 brand to Mercedes");
            System.out.println("Car2: " + car2.getBrand());

            car3.setModel("RS5");
            System.out.println("Set car3 model to RS5");
            System.out.println("Car3: " + car3.getModel());
        }
}
```


## Aufgabe 3: `Cargo` und `Box`-Klassen

> [!Aufgabe]
> Schreiben Sie eine Klasse `Cargo`, welche ein Stückgut mit Länge, Breite, Höhe und einem Namen modelliert (z.B. 30, 44, 65, "Kaffeemaschine"). Schreiben Sie einen Konstruktor, Getter und Setter für alle Instanzvariablen und eine Methode `toString`.
> 
> Schreiben Sie eine Klasse `Box`, die Instanzvariablen für die Länge, Breite und Höhe einer Box enthält. Zusätzlich enthält die Klasse `Box` eine Instanzvariable `full` vom Typ boolean, die angibt, ob die Box gefüllt ist oder nicht, sowie eine Instanzvariable `cargo` vom Typ `Cargo`. Der Konstruktor setzt die Länge, Breite und Höhe einer Box gemäss Parametern – neu instanziierte `Box` Objekte sollen standardmässig leer sein. Definieren Sie einen zweiten Konstruktor ohne Parameter, der eine Standard-Box mit Länge, Breite und Höhe 1 generiert. Zusätzlich definieren Sie eine Methode `getCapacity`, die das Volumen der Box berechnet und zurückgibt.
> 
> Schliesslich schreiben Sie eine Methode `addCargo`, welche ein Objekt vom Typ `Cargo` als Parameter entgegennimmt. Falls dieses Stückgut gemäss Länge, Breite und Höhe in die Box passt, passen Sie die Variable `full` und die Instanzvariable `cargo` an und geben `true` zurück (andernfalls `false`).
> 
> Testen Sie die Klasse `Box`, indem Sie in einer weiteren Klasse `BoxTest` drei `Box` Objekte instanziieren, manipulieren und ausgeben.

### Mögliche Lösung

#### Klasse `Cargo`

```java
public class Cargo {
    
    private String name;
    private int length;
    private int width;
    private int height;

    public Cargo(String name, int length, int width, int height) {
        this.name = name;
        this.length = length;
        this.width = width;
        this.height = height;
    }

    public String getName() {
        return this.name;
    }

    public int getLength() {
        return this.length;
    }

    public int getWidth() {
        return this.width;
    }

    public int getHeight() {
        return this.height;
    }

    public void setName(String name) {
        this.name = name;
    }

    public void setLength(int length) {
        if (length > 0) {
            this.length = length;
        }
    }

    public void setWidth(int width) {
        if (width > 0) {
            this.width = width;
        }
    }

    public void setHeight(int height) {
        if (height > 0) {
            this.height = height;
        }
    }

    public String toString() {
        return "Cargo: \tName: " + this.name + " Dimensions: " + this.length + "x" + this.width + "x" + this.height;
    }
}
```

#### Klasse `Box`

```java
import java.util.ArrayList;
import java.util.Collections;


public class Box {
    
    private Cargo cargo;
    private boolean isFull;
    private int length;
    private int width;
    private int height;

    public Box(int length, int width, int height) {
        this.length = length;
        this.width = width;
        this.height = height;
        this.isFull = false;
    }

    public Box() {
        this(1, 1, 1); // refers to the other constructor
    }

    public int getCapacity() {
        return this.length * this.width * this.height;
    }

    public int getLength() {
        return this.length;
    }

    public int getWidth() {
        return this.width;
    }   

    public int getHeight() {
        return this.height;
    }

    public boolean getIsFull() {
        return this.isFull;
    }

    public Cargo getCargo() {
        return this.cargo;
    }

    public void setLength(int length) {
        if (length > 0) {
            this.length = length;
        }
    }

    public void setWidth(int width) {
        if (width > 0) {
            this.width = width;
        }
    }

    public void setHeight(int height) {
        if (height > 0) {
            this.height = height;
        }
    }

    public boolean addCargo(Cargo cargo) {
        if (this.isFull) {
            System.out.println("Box already full");
            return false;

        /*
         * System welches sicherstellt, dass das Cargo schlau eingepackt wird. Box kann ja gedreht werden
         * ArrayList<Integer> erstellt einen Array
         */
        } else { 
            ArrayList<Integer> cargoDimensions = new ArrayList<>();
                cargoDimensions.add(cargo.getLength());
                cargoDimensions.add(cargo.getWidth());
                cargoDimensions.add(cargo.getHeight());
            ArrayList<Integer> boxDimensions = new ArrayList<>();
                boxDimensions.add(this.length);
                boxDimensions.add(this.width);
                boxDimensions.add(this.height);

            Collections.sort(cargoDimensions);
            Collections.sort(boxDimensions);
            
            boolean fits = true;
            for (int i = 0; i < 3; i++) {
                if (cargoDimensions.get(i) > boxDimensions.get(i)) {
                    fits = false;
                    break;
                }
            }

            if (fits) {
                this.cargo = cargo;
                this.isFull = true;
                System.out.println("Cargo placed in Box!");
                return true;
            } else {
                System.out.println("Box dimensions are too small for that cargo");
                return false;
            }

            
        }
    }

    public void removeCargo() {
        this.cargo = null;
        this.isFull = false;
    }

    public String toString() {
        return "Box: \tDimensions: " + this.length + "x" + this.width + "x" + this.height + " Capacity: " + this.getCapacity() + " " + this.cargo;
    }
}
```

#### Klasse `BoxTest`

```java
public class BoxTest {
    
    public static void main(String[] args) {
        
        Cargo cargo1 = new Cargo("Kaffeemaschine", 30, 44, 65);
        Cargo cargo2 = new Cargo("Kühlschrank", 60, 60, 180);
        Cargo cargo3 = new Cargo("Küchentisch", 80, 120, 75);
        Cargo cargo4 = new Cargo("Küchenstuhl", 40, 40, 90);

        System.out.println("Cargo1: " + cargo1);
        System.out.println("Cargo2: " + cargo2);
        System.out.println("Cargo3: " + cargo3);
        System.out.println("Cargo4: " + cargo4);

        cargo1.setName("Espressomaschine");
        System.out.println("Set cargo1 name to Espressomaschine");
        System.out.println("Cargo1: " + cargo1.getName());

        cargo2.setLength(70);
        System.out.println("Set cargo2 length to 70");
        System.out.println("Cargo2: " + cargo2.getName() + " Length: " + cargo2.getLength());

        cargo3.setWidth(100);
        System.out.println("Set cargo3 width to 100");
        System.out.println("Cargo3: " + cargo3.getName() + " Width: " + cargo3.getWidth());

        cargo4.setHeight(100);
        System.out.println("Set cargo4 height to 100");
        System.out.println("Cargo4: " + cargo4.getName() + " Height: " + cargo4.getHeight());

        Box box1 = new Box(50, 50, 50);
        Box box2 = new Box(100, 100, 100);
        Box box3 = new Box();

        System.out.println("Box1: " + box1);
        System.out.println("Box2: " + box2);
        System.out.println("Box3: " + box3);

        box1.setLength(100);
        System.out.println("Set box1 length to 100");
        System.out.println("Box1: " + box1.getLength());

        box2.setWidth(50);
        System.out.println("Set box2 width to 50");
        System.out.println("Box2: " + box2.getWidth());

        box3.setHeight(100);
        System.out.println("Set box3 height to 100");
        System.out.println("Box3: " + box3.getHeight());

        System.out.println("\n" + cargo1);
        System.out.println( box1);
        System.out.println("Placing cargo1 in box1 (NOTE: Dimensions don't match up, Box has to be turned)");
        box1.addCargo(cargo1);
        System.out.println("Box1: " + box1.getCargo());

        System.out.println("Trying to add another cargo into the same Box");
        box1.addCargo(cargo2);

        System.out.println("\nEmpty Box1");
        box1.removeCargo();
        System.out.println(box1);

        cargo1.setWidth(50);
        System.out.println(cargo1);

        System.out.println("\n" + cargo1);
        System.out.println( box1);
        System.out.println("Placing cargo1 in box1 (NOTE: Dimensions don't match up, Box has to be turned)");
        box1.addCargo(cargo1);
        System.out.println("Box1: " + box1.getCargo());

        System.out.println("\nEmpty Box1");
        box1.removeCargo();
        System.out.println(box1);

        cargo1.setWidth(100);
        System.out.println(cargo1);

        System.out.println("\n" + cargo1);
        System.out.println( box1);
        System.out.println("Placing cargo1 in box1 (NOTE: Dimensions don't match up! Cargo won't fit)");
        box1.addCargo(cargo1);
        System.out.println("Box1: " + box1);


    }
}
```


## Aufgabe 4: `Book`-Klasse Erweiterung

> [!Aufgabe]
> Auf ILIAS (Übungen → Serie 3) finden Sie eine Datei `Book.java`. Ihre Aufgabe ist es die darin implementierte Klasse `Book` wie folgt zu erweitern:
> 
> 1. Schreiben Sie einen Konstruktor sowie Getter und Setter für alle Instanzvariablen.
> 2. Implementieren Sie die Methode `age`, welche das Alter eines Buches (Anzahl Tage seit Erscheinungsdatum) berechnet und zurückgibt.
> 3.  Implementieren Sie die Methode `toString`, die alle Informationen eines `Book`-Objekts als String zurückgibt. Beispiel: 123, Die Blechtrommel, Günter Grass, 1.1.1959
> 4. Vervollständigen Sie die Methode `input`, welche die Werte für `id`, `title`, `author` und `dateOfPublication` von der Kommandozeile vom Benutzer einliest und im jeweiligen `Book`-Objekt abspeichert. Ungültige Eingaben müssen Sie nicht abfangen.
> 
> Testen Sie sämtliche Methoden der Klasse `Book` in einer zusätzlichen Klasse `BookShelf`.
