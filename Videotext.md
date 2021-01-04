# Projekt SWEN – GIT zur verteilten Software Entwicklung
## Vorlesetext im Lehrvideo

### Implikationen für Softwarearchitektur
Die verteilte Arbeitsweise mit Git ist gut mit den Vorgehensweisen der objektorientierten Programmierung vereinbar. Die zugrundeliegende Überlegung der klar eingegrenzten Bereiche in der Objektorientierung ist nämlich genau die Arbeitsweise, die ein Team braucht, das mit Git arbeitet, um möglichst wenige Merge-Konflikte zu erzeugen.
Jedes Mal, wenn verschiedene Entwickler nämlich gleichzeitig an derselben Stelle im Code arbeiten, kann es zu Merge-Konflikten kommen. Hier tritt also doppelt geleistete Arbeit auf, die zu allem Überfluss dann noch entwirrt werden muss.
Aufgaben verschiedener Entwickler können beim objektorientierten Programmieren auf verschiedene Objekte verteilt werden. Um Merge-Konflikte zu verhindern, werden abgeschlossene Objekte von Git erkannt und können auf verschiedene Dateien verteilt werden.
Aber auch wenn mehrere Entwickler an einem Objekt arbeiten, kann ein am Anfang festgelegtes öffentliches Interface zum weitgehend selbständigen Arbeiten an abgegrenzten Aufgaben beitragen. Der Entwickler arbeitet dann nämlich hauptsächlich an privaten Methoden, die wiederum abgeschlossene Einheiten sind. Diese Einheiten können von Git leicht erkannt, oder sogar vom Entwickler in eigene Dateien ausgelagert werden. Die verschiedenen Entwickler müssen dann nur noch über Veränderungen im öffentlichen Interface miteinander kommunizieren, um die privaten Methoden im Programmablauf zu kombinieren.
Der Pol der möglichst feingranularen Arbeitsaufteilung steht hier dem Vermeiden von Redundanzen im Code gegenüber. In der Planungsphase im Vorfeld muss ein geeignetes Mittelmaß dieser beiden Ideale gefunden werden.
