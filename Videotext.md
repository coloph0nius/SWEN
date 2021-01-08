# Projekt SWEN – GIT zur verteilten Software Entwicklung
## Vorlesetext im Lehrvideo

### Einleitung
Git ist ein verteiltes Versionsverwaltungssystem, das eine nicht-lineare Entwicklung ermöglicht.
Die grundlegende Funktion von Git ist das Erstellen von Commits. Das sind Momentaufnahmen des Codes zu einer bestimmten Zeit.
Bevor der Entwickler einen Commit erstellt, gibt er Git mit einer Reihe von Befehlen zu verstehen, welche Änderungen getrackt werden sollen. [git add / git rm im Video]
Git speichert dann beim Committen, was sich zum vorigen Commit verändert hat. [git commit -m im Video]
Der Entwickler kann in seinem Git-Repository zu einem späteren Zeitpunkt zu jedem dieser Commits wieder zurückwechseln.

#### Vorstellung Beispiel-Projekt
Zur anschaulichen Darstellung, wie GIT funktioniert haben wir uns ein Beispiel-Szenario überlegt. Mit diesem werden wir dann die Funktionsweise von GIT erklären.
Das Beispiel-Projekt besteht aus drei Klassen: eine GUI-Klasse,die die Oberfläche beschreibt, eine Controller-Klasse, die das Backend und die Oberfläche verbindet, und eine Klasse, die für das Backend und die Datenbankverbindung zuständig ist.

### Branching
Branching ist eines der wichtigsten Bestandteile von GIT. In GIT wurden Branches sehr einfach und schlank implementiert, wodurch schnell und ohne Probleme mit ihnen gearbeitet werden kann.
In der verteilten Softwareentwicklung helfen sie vor allem den Entwicklern unabhängig und mit geringen Konflikten gleichzeitig an einem Projekt zu arbeiten, wodurch das Team vor Störungen durch instabile Features geschützt ist.

### Branching Strategien
Branching Strategien geben eine Art Vorgehensmodell der Entwicklung vor, in dem sie bestimmte Branches mit einem zugeteilten Zweck implementieren. Branching Strategien helfen vor allem dem Projektmanagement bei der Organisation und bei der Unterstützung von Vorgehensmodellen wie Scrum. Branching Strategien sorgen aber auch für einen gewisse Ordnung innerhalb des Entwicklungsprozesses.

#### Feature Branching
Feature Branching ist die erste Branchingstrategie, die wir uns anschauen werden. Es ist eine einfache und offene Strategie. Es wird, wie der Name schon impliziert für jedes Feature des Projektes ein neuer Branch angelegt. Dadurch ist die Entwicklung eines Features separiert von der Mainline, wodurch der Entwickler ungestört an dem Feature arbeiten kann ohne, dass Probleme mit dem fertigen Release entstehen. Wurde ein Feature fertig implementiert und getestet, wird der zugehörige Feature-Branch in den master gemerged.

#### Gitflow
Gitflow wirkt auf den ersten Blick im Gegensatz zu den vorherigen Branching Strategien sehr kompliziert, doch eigentlich verbindet Gitflow nur das Release Branching mit dem Feature Branching.
Wie bei den vorherigen Strategien befinden sich auf dem Master nur stabile und fertige Versionen des Projektes. Der Hotfix Branch dient zur Implementierung kleiner dringender Änderungen und zur Fehlerbehebung.
Die eigentliche Entwicklung passiert in den beiden Feature-Branches, sobald ein Feature fertig implementiert wurde, wird es in den Devleop-Branch gemerged um Merg-Konflikte mit anderen Features zu bereinigen. Ist die Entwicklung komplett abgeschlossen wird der Develop-Branch in den Release-Branch integriert, um danach in den Master-Branch aufgenommen zu werden.

### Merging
Das Zusammenführen zweier Branches nennt man Merging. Somit können zwei Versionsstände eines Projektes zusammengeführt werden. Merge-konflikte entstehen, wenn in einer Datei an derselben Stelle in beiden Branches unterschiedliche Änderungen vorgenommen wurden.
GIT unterstützt den Entwickler beim Merging durch eine Übersicht an geänderten Dateien mit ihren Änderungen für die beiden Branches. Dadurch kann jedes Teammitglied einen Merge durchführen, ohne selbst an den Branches gearbeitet zu haben. Merge-Konflikte sind in unserer verteilten Arbeitweise unerwünscht, um diese weitesgehend zu Vermeiden, müssen wir unsere Softwarearchitektur an unsere Arbeitsweise anpassen.

### Implikationen für Softwarearchitektur
Die verteilte Arbeitsweise mit Git ist gut mit den Vorgehensweisen der objektorientierten Programmierung vereinbar. Die zugrundeliegende Überlegung der klar eingegrenzten Bereiche in der Objektorientierung ist nämlich genau die Arbeitsweise, die ein Team braucht, das mit Git arbeitet, um möglichst wenige Merge-Konflikte zu erzeugen.
Jedes Mal, wenn verschiedene Entwickler gleichzeitig an derselben Stelle im Code arbeiten, kann es zu Merge-Konflikten kommen. Hier tritt also doppelt geleistete Arbeit auf, die zu allem Überfluss dann noch entwirrt werden muss.
Aufgaben verschiedener Entwickler können beim objektorientierten Programmieren auf verschiedene Objekte verteilt werden. Um Merge-Konflikte zu verhindern, werden abgeschlossene Objekte von Git erkannt und können auf verschiedene Dateien verteilt werden.
Aber auch wenn mehrere Entwickler an einem Objekt arbeiten, kann ein am Anfang festgelegtes öffentliches Interface zum weitgehend selbständigen Arbeiten an abgegrenzten Aufgaben beitragen. Der Entwickler arbeitet dann nämlich hauptsächlich an privaten Methoden, die wiederum abgeschlossene Einheiten sind. Diese Einheiten können von Git leicht erkannt, oder sogar vom Entwickler in eigene Dateien ausgelagert werden. Die verschiedenen Entwickler müssen dann nur noch über Veränderungen im öffentlichen Interface miteinander kommunizieren, um die privaten Methoden im Programmablauf zu kombinieren.
Der Pol der möglichst feingranularen Arbeitsaufteilung steht hier dem Vermeiden von Redundanzen im Code gegenüber. In der Planungsphase im Vorfeld muss ein geeignetes Mittelmaß dieser beiden Ideale gefunden werden.

### Dokumentationsmöglichkeiten in Git
Um in großen, kollaborativen Software-Bibliotheken den Überblick über Veränderungen zwischen Commits und Features der Software zu behalten, ist eine vollständige Dokumentation unerlässlich.
Git unterstützt das, indem es den Entwickler dazu auffordert, zu jedem Commit eine Commit-Nachricht zu verfassen.
Außerdem bieten die gängigen Git-Server wie Github oder Gitlab Ünterstützung für Textformatierung in Markdown-Notation. Markdown vereinfacht das schnelle erstellen von leicht renderbaren, übersichtlichen Readmes, Changelogs und ähnlichem.


### Fazit
Letzlich ist zu Sagen, dass GIT für eine effektive verteilte Software entwicklung unabdingbar ist. Wenn wir uns noch an ein paar Grundregeln zur Arbeitsweise mit GIT halten, kann der Entwicklungsprozess nahezu Reibungslos ablaufen. Wichtig sind aussagekräftige Commit-Messages, denn durch diese wird fast automatisch eine kleine Dokumentation über unser Projekt erstellt. Abstraktion unseres Codes ist auch ein wichtiges Grundprinzip, denn die Vermeidung von Merge-Konflikten beschleunigt unsere Entwicklung maßgeblich. Schließlich ist es noch hilfreich, wenn wir für unser Projekt je nach Vorgehens-Modell eine sinnvolle Branching-Strategie wählen, nach der wir unser Projekt entwickeln.

### Checkout
Der aktuelle Stand eines jeden Branches kann mit dem Befehl "git checkout" eingesehen werden. Git wendet dann alle nötigen Veränderungen auf das lokale Repository an, sodass es sich auf dem Stand des gewünschten Branches befindet.

### Diff
Mit dem Befehl "git diff" kann man sich auch anzeigen lassen, was sich zwischen zwei Commits verändert hat, oder wie sich zwei branches voneinander unterscheiden. Commits können dabei über ihren Hash spezifiziert werden. Branch-Namen werden durch zwei Punkte voneinander getrennt.



