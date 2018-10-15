% Akaflieg Python Tutorial

# Installation

* Anaconda
## Versionen
Python gibt es momentan noch in zwei Versionen: Python 2 und Python 3. Die beiden Versionen sind zwar ähnlich, dürfen aber nicht als austauschbar gesehen werden. Python 2 wird nur noch bis 2020 weiterentwickelt und sollte allein deshalb nicht mehr verwendet werden. Trotzdem muss man beachten dass manche Beispiele im Internet nur unter Python 2 funktionieren und ein wenig angepasst werden müssen.

# Grundlagen

## Hallo Welt

### Prompt
Es gibt veschiedene Arten und weisen ein Python-Befehle auszuführen. Die einfachste und schnellste Art und weise ist in einer Prompt. Eine Prompt ist ein CMD-Fenster in das man Python-Code schreiben kann, der sofort ausgeführt wird. Das ist praktisch um schnell kleine Programm-Schnipsel zu testen aber nicht um ein volles Programm zu schreiben.

Wir wollen so ein "Hallo Welt"-Programm testen. Öffnet man die Prompt kann man den Befehl um "Hallo Welt" auszugeben direkt eingeben. Aussehen sollte das so:
```
>>>print("Hallo Welt!")
Hallo Welt!
```

### Datei
Eine praktischere Möglichkeit ein Programm auszuführen ist es in eine Datei zu schreiben und dann den Python Interpreter mit dieser Datei aufzurufen. Dazu schreibt man zum Beispiel eine Datei mit dem Inhalt:
```
print("Hallo Welt!")
```
und ruft aus einem Terminal (CMD) das Skript auf.
```
>python hallo.py
Hallo Welt!
```

### Notebook
Eine komfortable Option in Python zu programmieren sind IPython/Jupyter Notebooks. Ein Notebook ist eine Datei die aus einer Mischung aus Text und Code besteht. So eine Datei ist aus jeweiligen Blöcken aufgebaut. Diese Blöcke können einzeln ausgeführt, bearbeitet und Verschoben werden.
Erstellt man einen Code Block mit der Schaltfläche mit dem Plus kann man dort den jeweilgen Teil des Programms eingeben und dann mit Shift+Enter ausführen.
In einem Textblock kann auch LaTeX Math verwendet werden um Formeln darzustellen.

## Variablen (Basis)
Um ein paar Python ausdrücke auszuprobieren wollen wir ein paar einfache Rechnungen anstellen.
Das funktioniert ziemlich genau wie man das Erwartet, bzw. von Matlab etc kennt.
```
>>> 2 + 2
4
>>> 1 - 2*2
-3
>>> 5/2
2.5
```

Eine Zahl ohne Komma heißt ein Integer. Ein Integer kann nur ganzzahlen darstellen.
Der Teilen-Operator '/' liefert aber immer eine Kommazahl zurück, zu erkennen and dem Nachkommateil.

```
>>> 2/3
0.6666666666667
>>> 2/2
1.0
```

Ganzzahlige Division nutzt den Operator '//'.
```
>>> 17//3
5
```

Weitere Operatoren sind '\*\*' für Potenzen und '%' für Modulo.

Man kann eine Zahl in einer Variable speichern durch eine Zuweisung.
```
>>> nichtpi = 3
>>> print(nichtpi)
3
>>> print(nichtpi + 1)
4
```

Wenn man Texte verarbeitet, nutzt man Strings, den Datentyp für Zeichenketten.
Strings kann man entweder mit einfachen Hochkommas ', oder doppelten Hochkommas erzeugen ".
Will man zwei Strings aneinander hängen kann man das mit dem '+' Operator.
```
>>> print("Hello")
Hello
>>> print("Hello" + " World")
Hello World
```

Will man Variablen in einen String einfügen kann man das mit dem '.format' Befehl.
Man ruft die Methode 'format' des Strings auf und übergibt diesem die Variablen die man Einfügen möchte.
Die Stelle an der man die Variable einfügen möchte markiert man mit '{}'. Das geht mit beliebig vielen Variablen.
```
>>> projektnummer = 45
>>> print("D-{}".format(projektnummer))
D-45
>>> print("{} + {} = {}".format(1, 2, 1+2))
1 + 2 = 3
```

Eine weitere Art des Datentyps ist ein Wahrheitswert, genannt 'boolean'. Ein boolean kann entweder 'True' oder 'False' sein. Boolean sind insbesondere Interessant für If-Abfragen.
Operatoren auf Boolean sind:
* Und: ```&```
* Oder: ```|```
* Nicht ```!```
* XOR: ```^```

Einige dieser Operatoren kann man auch einfach ausschreiben:
```
>>> True and False
False
>>> False or True
True
>>> not True
False
```

Will man Zahlen miteinander vergleichen gibt es einige Operatoren für Zahlen die Wahrheitswerte liefern:
* Echt kleiner: ```<```
* Kleiner gleich: ```<=```
* Gleich: ```==```
* Größer gleich: ```>=```
* Echt größer: ```>```
* Ungleich: ```!=```

```
>>> 2 < 3
True
>>> 1 + 1 == 2
True
```

## if else und elif
Will man in seinem Programm unterschiedliche Sachen für unterschiedliche Fälle machen benutzt man eine If-Abfrage. In eine If-Abfrage schreibt man einen Ausdruck der einen Boolean ergibt gefolgt von einem Doppelpunkt und einer neuen Zeile. Alles was dann in und nach der neuen Zeile eingerückt steht wird ausgeführt falls der Wert des Boolean True ist.
```
passwort = 'abcdef'
eingabe = 'letmein'

if passwort == eingabe:
  print('access granted')
```

Führt zu:
```access granted```

Will man noch zusätzlich abfragen ob die Bedingung nicht erfüllt ist benutzt man ein ```else```.

```
n = 1234

if n % 2 == 0:
  print("n ist gerade")
else:
  print("n ist nicht gerade")
```

Führt zu:
```n ist gerade```

Hat man allerdings den Fall dass man zwischen mehr als Zwei Fällen unterscheiden will kann man ein else mit einem if verbinden. Ein ```elif```. Ein elif wird nur ausgewertet wenn das vorherige if falsch war und die aktuelle Bedingung wahr ist.
```
stunde = 12

if stunde < 10:
  print("Guten Morgen.")
elif stunde < 14:
  print("Guten Mittag.")
else:
  print("Guten Abend.")
```

## Schleifen
Will man ein Stück Code öfter hintereinander ausführen benutzt man Schleifen. Die wichtige Schleife in Python ist die for-Schleife. Eine for-Schleife führt einen Code Block für jedes Element eines Containers aus (Ein Container ist sowas wie eine Menge/Liste, mehr später).
Zunächst ist es wichtig dass wir eine Liste von Zahlen mit dem ```range``` Befehl erzeugen können.
```
>>> for i in range(10):
      print("{} Bier".format(i))
0 Bier
1 Bier
2 Bier
3 Bier
4 Bier
5 Bier
6 Bier
7 Bier
8 Bier
9 Bier
```

Den Range-Befehl kann man auf drei Arten aufrufen.
Mit nur einem Argument (0 bis):
```
>>> range(5)
[0, 1, 2, 3, 4]
```

Mit zwei Argumenten (von bis):
```
>>> range(5, 10)
[5, 6, 7, 8, 9]
```

Mit drei Argumenten (von bis mit Schrittweite):
```
>>> range(0, 1, 0.2)
[0, 0.2, 0.4, 0.6, 0.8]
```

Die Zweite, weniger verwendete, Art einer Schleife ist die ```while```-Schleife. Die While-Schleife führt so lange aus wie eine Bedingung gilt.
```
>>> f = 1.0
>>> while f > 0.1:
      f = f/2
>>> f
0.0625
```

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

## Erstellen von Arrays

## Zugriff auf Array-Elemente

## Rechenoperationen mit Arrays

# Plotten (matplotlib)

# Sonstiges

## Minimierung/Optimierung (scipy)
