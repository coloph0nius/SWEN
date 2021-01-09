# Projekt SWEN – GIT zur verteilten Software Entwicklung
## Vorlesetext im Lehrvideo

### Einleitung / Inhalt
Herzlich Willkommen zu diesem Lernvideo, in dem gezeigt wird, wie git uns bei einer verteilten Softwareentwicklung unterstützt. 

### Einleitung / Überblick über GIT
Zunächst wollen wir einen kurzen Überblick über die Konzepte von GIT schaffen.
Git ist ein verteiltes Versionsverwaltungssystem, das eine nicht-lineare Entwicklung ermöglicht.
Die grundlegende Funktion von Git ist das Erstellen von Commits. Das sind Momentaufnahmen des Codes zu einer bestimmten Zeit.
Bevor der Entwickler einen Commit erstellt, gibt er Git mit einer Reihe von Befehlen zu verstehen, welche Änderungen getrackt werden sollen. [git add / git rm im Video]
GIT erstellt bei jedem Commit einen Schnappschuss des Projekts. Damit wird jeder zwischenstand des Projektes in git gespeichert.[git commit -m im Video]
Der Entwickler kann in seinem Git-Repository zu einem späteren Zeitpunkt zu jedem dieser Commits wieder zurückwechseln.

### Branching
Branching ist ein Zentraler Bestandteil von GIT. In GIT wurden Branches sehr einfach und schlank implementiert, wodurch schnell und ohne Probleme mit ihnen gearbeitet werden kann.
In der verteilten Softwareentwicklung helfen sie vor allem den Entwicklern unabhängig und mit geringen Konflikten gleichzeitig an einem Projekt zu arbeiten, wodurch das Team vor Störungen durch instabile Features geschützt ist.
Branches sind eine Abzweigung, von der Hauptentwicklungslinie, das ermöglicht es, neue Features erst zu implementieren, wenn sie wirklich fertig sind.

### Branching Strategien
Durchgeführt wird das Branching nach einer bestimmten Strategie, die eine Art Vorgehensmodell der Entwicklung vorgibt. So erhält jeder Branch einen bestimmten Zweck.Branching Strategien helfen vor allem dem Projektmanagement bei der Organisation und bei der Unterstützung von Vorgehensmodellen wie Scrum. Branching Strategien sorgen aber auch für einen gewisse Ordnung innerhalb des Entwicklungsprozesses.

#### Feature Branching
Feature Branching ist die erste Branchingstrategie, die wir uns anschauen werden. Es ist eine einfache und offene Strategie. Das bedeutet, das dem Entwicklerteam viel Freiraum bei der Umsetzung dieser Strategie bleibt.
Diese Strategie ist gut für lineare Vorgehensmodelle, wie zum Beispiel dem Wasserfallmodell geeignet.
Es wird, wie der Name schon impliziert für jedes Feature des Projektes ein neuer Branch angelegt. Dadurch ist die Entwicklung eines Features separiert von der Mainline, wodurch der Entwickler ungestört an dem Feature arbeiten kann ohne, dass Probleme mit dem fertigen Release entstehen. Wurde ein Feature fertig implementiert und getestet, wird der zugehörige Feature-Branch in den master gemerged.

#### Gitflow
Gitflow wirkt auf den ersten Blick im Gegensatz zu der vorherigen Branching Strategie sehr komplex, doch eigentlich verbindet Gitflow nur das Feature Branching mit agilen Vorgehensweisen.
Im Gegensatz zum Feature Branching, bleibt den Entwicklern weniger Freiraum.
Wie bei den vorherigen Strategien befinden sich auf dem Master nur stabile und fertige Versionen des Projektes. Der Hotfix Branch dient zur Implementierung kleiner dringender Änderungen und zur Fehlerbehebung.
Die eigentliche Entwicklung passiert in den beiden Feature-Branches, sobald ein Feature fertig implementiert wurde, wird es in den Devleop-Branch gemerged um Merg-Konflikte mit anderen Features zu bereinigen. Ist die Entwicklung komplett abgeschlossen wird der Develop-Branch in den Release-Branch integriert, um danach in den Master-Branch aufgenommen zu werden.

### Merging
Das Zusammenführen zweier Branches nennt man Merging. Somit können zwei Versionsstände eines Projektes zusammengeführt werden. Merge-konflikte entstehen, wenn in einer Datei an derselben Stelle in beiden Branches unterschiedliche Änderungen vorgenommen wurden.
GIT unterstützt den Entwickler beim Merging durch eine Übersicht an geänderten Dateien mit ihren Änderungen für die beiden Branches. Dadurch kann jedes Teammitglied einen Merge durchführen, ohne selbst an den Branches gearbeitet zu haben. Merge-Konflikte sind in unserer verteilten Arbeitweise unerwünscht, um diese weitesgehend zu Vermeiden, müssen wir unsere Softwarearchitektur an unsere Arbeitsweise anpassen.

### Implikationen für Softwarearchitektur
Die verteilte Arbeitsweise mit Git ist gut mit den Vorgehensweisen der objektorientierten Programmierung vereinbar. Die zugrundeliegende Überlegung der klar eingegrenzten Bereiche in der Objektorientierung ist nämlich genau die Arbeitsweise, die ein Team braucht, das mit Git arbeitet, um möglichst wenige Merge-Konflikte zu erzeugen.
Aufgaben verschiedener Entwickler können beim objektorientierten Programmieren auf verschiedene Objekte verteilt werden. 
Merge Konflikte, werden effektiv vermieden, wenn an jedem Modul nur ein Entwickler arbeiten. Also ist es hilfreich, wenn Projektmodule klar voneinander abgegrenzt sind. 
Dieses Prinzip nennt man Modularität.
Dadurch treten Merge Konflikte nur noch an Stellen auf, an denen Module zusammengeführt werden, wie zum Beispiel Interfaces.

### Dokumentationsmöglichkeiten in Git
Um in großen, kollaborativen Software-Bibliotheken den Überblick über Veränderungen zwischen Commits und Features der Software zu behalten, ist eine vollständige Dokumentation unerlässlich.
Git unterstützt das, indem es den Entwickler dazu auffordert, zu jedem Commit eine Commit-Nachricht zu verfassen. Wenn diese Commit-Messages konsequent sinnvoll formuliert sind, wird dadurch schon eine leicht nachvollziehbare Dokumentation erstellt.
Außerdem bieten die gängigen Git-Plattformen wie Github oder Gitlab Ünterstützung für Textformatierung in Markdown-Notation. Markdown vereinfacht das schnelle erstellen von leicht darstellbaren und übersichtlichen Readmes, Changelogs und ähnlichem.


### Fazit
Letzlich ist zu Sagen, dass GIT für eine effektive verteilte Software entwicklung unabdingbar ist. Wenn wir uns noch an ein paar Grundregeln zur Arbeitsweise mit GIT halten, kann der Entwicklungsprozess nahezu Reibungslos ablaufen. Wichtig sind aussagekräftige Commit-Messages, denn durch diese wird fast automatisch eine kleine Dokumentation über unser Projekt erstellt. Abstraktion unseres Codes ist auch ein wichtiges Grundprinzip, denn die Vermeidung von Merge-Konflikten beschleunigt unsere Entwicklung maßgeblich. Schließlich ist es noch hilfreich, wenn wir für unser Projekt je nach Vorgehens-Modell eine sinnvolle Branching-Strategie wählen, nach der wir unser Projekt entwickeln.



