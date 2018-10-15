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

* Zahlen

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

## Erstellen von Arrays

## Zugriff auf Array-Elemente

## Rechenoperationen mit Arrays

# Plotten (matplotlib)

# Sonstiges

## Minimierung/Optimierung (scipy)
