% Akaflieg Python Tutorial

# Installation

* Anaconda
* Versionen

# Grundlagen

## Hallo Welt

print

repl
datei
notebook

## Variablen (Basis)

* Zahlen

	* Grundrechenkram
	* True-divide, floor-divide

* Wahrheitswerte

* Strings (auch format Befehl)

## If und Else und elif

## Schleifen

for-Schleife
while

## Container

* Tupel

* Liste
  * Slicing

* Dictionary

iterieren über Containerwerte
list comprehensions

## Funktionen

* normale Funktionsdefiniton

* lambda Gerät

* call by reference/value

* sichtbarkeit global/lokal

## Klassen

# Matrizenrechnung (numpy)

Das numpy-Paket ist einer der Grundpfeiler für wissenschaftliches Programmieren in Python. Es stellt mit dem array-Objekt eine Datenstruktur zur Verfügung, die in der Lage ist N-dimensionale Matrizen abzubilden. Grundlegende Funktionen zum Arbeiten mit dem array-Objekt gehören außerdem zu numpy.

Um das numpy-Paket nutzen zu können, muss es zuerst eingebunden werden. Dies geschiet meist mit folgendem Aufruf:

```
import numpy as np
```

Damit wir das numpy-Paket geladen und unter dem Bezeichner 'np' zur Verfügung gestellt.

## Erstellen von Arrays

Das Erstellen von Arrays kann auf zahlreichen Wegen geschehen. Oft werden Arrays mithilfe von Listen erstellt. Ein eindimensionales Array mit den Einträgen 1, 2 und 3 erzuegt folgender Befehl:

```
a = np.array([1,2,3])
```

Der Zugriff auf Elemente des eindimensionalen Arrays erfolgt mit eckigen Klammern. Die Indizes zum Zugriff auf Werte beginnen bei 0. Für den ersten Array-Eintrag muss folgender Befehl ausgeführt werden:

```
>>> a[0]
1
```

Die Einträge lassen sich durch Überschreiben mit neuen Werten ändern:

```
>>> a[0] = 5
>>> a
[5,2,3]
```

Wird ein eindimensionales Array mit einer Reihe von Einträgen konstanten Abstandes benötigt, kann die Funktion *arange* verwendet werden:

```
>>> np.arange(1,4,1)
[1,2,3]
```

Der erste übergebene Parameter bildet den Startwert, während der zweite das Ende darstellt. Mit dem dritten Parameter wird der Abstand zwischen den Array einträgen festeglegt. Es lassen sich für alle Parameter nicht ganzzahlige Werte übergeben. Ist der Abstand zwischen benachbarten Array-Einträgen unwichtig, aber die Anzahl von Werten festgelegt kann *linspace* verwendet werden:

```
>>> np.linspace(1, 2, 101)
[1.0, 1.01, 1.02, ... , 1.99,2.00]
```

Neben eindimensionalen Arrays können mehrdimensionale Arrays durch geschachtelte Listen erzeugen. Ein zweidimensionales Array wird beispielsweise mit folgendem Aufruf erstellt:

```
b = np.array([[1,2,3],[4,5,6]])
```

Der Inhalt von *b* lässt sich als Matrix darstellen:

$$ \boldsymbol{b} = \begin{pmatrix} 1 & 2 & 3 \\ 4 & 5 & 6\end{pmatrix}$$

Es gibt 2 Zeilen und 3 Spalten. Diese Größe lässt sich direkt über die *shape*-Eigenschaft ermitteln:

```
>>> b.shape
(2,3)
```

Der Zugriff auf einzelne Elemente erfolgt jetzt über die Angabe der gewünschten Zeile und Spalte

```
>>> b[1,1]
5
```

Statt der Listen können auch Tuple verwendet werden um Arrays zu initialisieren. Weiterhin gibt es zahlreiche Funktionen spezielle Matrixformen zu erzeugen. Mit *zeros* kann zum Beispiel ein Array definierter Größe erstellt werden, dessen Einträge alle zu Null gesetzt sind.

```
>>> np.zeros((3, 3))
[[0, 0, 0], [0, 0, 0], [0, 0, 0]]
```

Analog dazu existiert eine Funktion *ones*, die alle Einträge mit Eins initialisiert. Ein Array definierter Größe mit beliebigem konstanten Wert kann wird mit *full* erzeugt:

```
>>> np.full((3, 3), 3.4)
[[3.4, 3.4, 3.4], [3.4, 3.4, 3.4], [3.4, 3.4, 3.4]]
```

Zum Erstellen der Einheitsmatrix kann *eye* verwendet werden:

```
>>> np.eye((3, 3))
[[1.0, 0.0, 0.0],[0.0, 1.0, 0.0],[0.0,0.0,1.0]]
```

Außerdem existiert eine Funktion zur Initialisierung mit zufälligen Werten:

```
>>> np.random.random((3, 3))
```

## Rechenoperationen mit Arrays

Berechnungen mit Arrays gleicher Größe erfolgen im Normalfall Elementweise. So wird die Addition von Arrays mit dem *+*-Operator oder der *add*-Funktion elementweise durchgeführt:

```
>>> a1 = np.array([[1.2, 1.3],[0.9, 1.2]])
>>> a2 = np.ones((2,2))
>>> a1 + a2
[[2.2, 2.3], [1.9, 2.2]]
>>> np.add(a1, a2)
[[2.2, 2.3], [1.9, 2.2]]
```

Analog erfolgt die elementweise Multiplikation von Arrays mit dem __*__-Operator oder der *multiply*-Funktion.

```
>>> a1 = np.array([[1.2, 1.3],[0.9, 1.2]])
>>> a2 = np.full((2,2),2)
>>> a1 * a2
[[2.4, 2.6], [1.8, 2.4]]
>>> np.multiply(a1, a2)
[[2.4, 2.6], [1.8, 2.4]]
```

Gleiches gilt für die Division, die mit dem Operator */* oder der Funktion *divide* erfolgt und die Subtraktion ( *-* und *subtract*).

Auf zweidimensionale Arrays kann auch das Matrixprodukt angewandt werden. Hierfür gibt es den Operator *@* und die Funktion *matmul*.

```
>>> a1 = np.array([[1.2, 1.3],[0.9, 1.2]])
>>> a2 = np.full((2,2),2)
>>> a1 @ a2
[[5.0, 5.0], [4.2, 4.2]]
>>> np.matmul(a1, a2)
[[5.0, 5.0], [4.2, 4.2]]
```

Außerdem kann für eindimensionale Arrays (Vektoren) mit der Funktion *dot* das Skalarprodukt (inneres Produkt) gebildet werden:

```
>>> a1 = np.array([1, 2, 2])
>>> a2 = np.array([2, 3, 2])
>>> np.dot(a1, a2)
[2, 6, 4]
```

Für das Kreuz- oder Vektorprodukt zweier 3D-Vektoren gibt es die *cross*-Funktion:

```
>>> a1 = np.array([1, 2, 2])
>>> a2 = np.array([2, 3, 2])
>>> np.cross(a1, a2)
[-2, 2, 1]
```

%TODO: sum, mean, etc

## Broadcasting

Bislang wurden Rechenoperationen immer mit Arrays gleicher Form (*shape*) durchgeführt. Liegen Arrays mit ungleicher Form vor, versucht *numpy* dennoch durch sogenanntest Broadcasting sinnvolle Rechenoperationen durchzuführen. Das einfachste Beispiel ist die Multiplikation eines zweidimensionalen Arrays (Matrix) mit einem Skalar. 

```
>>> a = np.array([1, 2, 2])
>>> b = 2.0
>>> a*b
[2, 4, 4]
```

Diese Operation führt zum gleichen Ergebnis wie

```
>>> a = np.array([1, 2, 2])
>>> b = np.array([2., 2., 2.])
>>> a*b
[2, 4, 4]
```

Der skalare Wert wird auf die gleiche Array-Größe gebracht, sodass eine elementweise Multiplikation möglich ist.

%TODO fertig machen

## Indexing

Der grundlegende Zugriff auf Elemente (Indexing) wurde bereits erklärt. In diesem Abschnitt werden weiterführende Aspekte der Indizierung erklärt. Soll beispielsweise auf das letzte Element in einer Dimension zugegriffen werden, kann der Index -1 verwendet werden:

```
>>> a = np.array([[1, 2, 2],[3,4,5]])
>>> a[-1, 1]
4
```

Oft ist es auch hilfreich auf eine ganze Zeile oder Spalte in einer Matrix zugreifen zu können. Hierfür wird analog zu Listen in der entsprechenden Dimension *:* verwendet:

```
>>> a = np.array([[1, 2, 2],[3,4,5]])
>>> a[-1,:]
[3,4,5]
```

Eine komplete Spalte einer Matrix ergibt entsprechend

```
>>> a[:,1]
[[2],[4]]
```

Der Doppelpunkt kann außerdem mit Grenzen verwendet werden, um nicht alle Werte der entspechenden Dimension auszuwählen.
 
# Plotten (matplotlib)

Das Standard-Paket zum Plotten ist [matplotlib](https://matplotlib.org/). Es stellt mit pyplot MATLAB ähnliche Funktionen für einfaches, schnelles Plotten zur Verfügung. Weiterführende Funktionen und ein objektorientiertes Interface erlauben den vollen Zugriff auf Plot-Eigenschaften. Im Folgenden werden Grundlagen vorgestellt. Zunächst wird das pyplot-Interface eingebunden:

```
>>> from matplotlib import pyplot as plt
```

Dieses steht jetzt unter *plt* zur Verfügung. Ein erster Sinus-Plot wird wie folgt erzeugt:

```
>>> x = np.linspace(0, 2*np.pi)
>>> y = np.sin(x)
>>> plt.plot(x, y)
>>> plt.show() # im jupyter notebook nicht notwendig
```

![sinus-plot](images/sinus.png)

Um ein Gitter anzuzeigen, wird die *grid*-Funktion verwendet. Achsenbeschriftungen werden mit *xlabel* und *ylabel* hinzugefügt. Die *title*-Funktion erlaubt das setzen eines Plot-Titels. 
Weitere Datenreihen können durch wiederholten Aufruf der *plot*-Funktion angezeigt werden. Damit *matplotlib* eine Legende erzeugen kann, kann hierbei ein Label (Parameter *label*) übergeben werden. Datenreihen mit angegebenem Label werden beim Aufruf der *legend*-Funktion automatisch in der Legende angezeigt.
Als Beispiel werden Sinus- und Cosinus-Funktion im gleichen Plot angezeigt.

```
>>> x = np.linspace(0, 2*np.pi)
>>> y1 = np.sin(x)
>>> y2 = np.cos(y)
>>> plt.plot(x, y1, label='Sinus')
>>> plt.plot(x, y2, label='Cosinus')
>>> plt.xlabel('x')
>>> plt.ylabel('y')
>>> plt.legend()
>>> plt.title('Toller Plot')
>>> plt.grid()
>>> plt.show() # im jupyter notebook nicht notwendig
```

![sinus-plot erweitert](images/sinus-extended.png)



# Sonstiges

## Minimierung/Optimierung (scipy)

## try und except

## import ausführlich
