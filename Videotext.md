# Projekt SWEN – GIT zur verteilten Software Entwicklung
## Vorlesetext im Lehrvideo

### Einleitung / Inhalt
Herzlich Willkommen zu diesem Lernvideo, in dem gezeigt wird, wie uns git bei einer verteilten Softwareentwicklung unterstützt. 

### Einleitung / Überblick über GIT
Zunächst wollen wir einen kurzen Überblick über die Konzepte von GIT schaffen.
Git ist ein verteiltes Versionsverwaltungssystem, welches eine nicht-lineare Entwicklung ermöglicht.
Die grundlegende Funktion von Git ist das Erstellen von Commits. Das sind Momentaufnahmen des Codes zu einem bestimmten Änderungszeitpunkt.
Bevor der Entwickler einen Commit erstellt, gibt er Git mit einer Reihe von Befehlen zu verstehen, welche Änderungen getrackt werden sollen. 
Zu Beginn wird mit git pull das eigene lokale Repository auf den neusten Stand gebracht. Danach wird an der Klasse MyClass.java gearbeitet, und die Änderungen gesichert. git nimmt die Änderungen erst mit dem Befehl git add MyClass.java in sein System auf. Mit git add lassen sich noch weiter Dateien aufnehmen. Mit git commit wird dann der eigentliche Commit erstellt. In dem message Feld sollte eine sinnvolle Beschreibung der Änderungen bzw. Inhalte des Commits stehen. 
GIT erstellt bei jedem Commit einen Schnappschuss des Projekts, sodass jeder Bearbeitungsstand in git hinterlegt ist.
Der Entwickler kann innerhalb des Repositories jederzeit zu einem beliebigen Commit springen.

### Branching
Branching ist ein zentraler Bestandteil von GIT. In GIT wurden Branches sehr einfach und schlank implementiert, dadurch kann schnell und ohne Probleme mit ihnen gearbeitet werden. Durch Branching wird es möglich, dass viele Entwickler gleichzeitig am Code arbeiten können. 
Branches sind eine Abzweigung von der Hauptentwicklungslinie. Das ermöglicht es, neue Features erst zu implementieren, wenn sie wirklich fertig sind.
So kann auf einem Branch beliebig programmiert und getestet werden, ohne dass das Hauptprojekt durch unfertige oder instabile Features unbenutzbar wird. Änderungen werden erst wieder in die Hauptlinie eingebracht, wenn sie zu 100% fertiggestellt sind. Dadurch ist das Team vor Störungen durch instabile Features geschützt.
Insbesondere in der verteilten Softwareentwicklung helfen sie den Entwicklern mit wenigen Konflikten gleichzeitig an einem Projekt zu arbeiten. Richtig angewandt, sorgen Branches dafür, dass unabhängig und ohne Konflikte mit vielen Personen an einem Projekt gearbeitet werden kann. 


### Branching Strategien
Durchgeführt wird das Branching nach einer bestimmten Strategie, die ein Vorgehensmodell der Entwicklung vorgibt. So erhält jeder Branch einen bestimmten Zweck. Branching Strategien helfen bei der Organisation des Projektes und bei der Unterstützung von Vorgehensmodellen wie etwa Scrum. Branching Strategien sorgen aber auch für Ordnung innerhalb des Entwicklungsprozesses.

#### Feature Branching
Feature Branching ist die erste Branchingstrategie, die wir uns anschauen werden. Es ist eine einfache und offene Strategie. Dem Entwicklerteam bleibt hierbei viel Freiraum bei der Umsetzung dieser Strategie.
Feature Branching ist gut für lineare Vorgehensmodelle, wie zum Beispiel dem Wasserfallmodell geeignet.
Es wird, wie der Name schon andeutet für jedes Feature des Projektes ein neuer Branch angelegt. Auf dem Beispielbild sind dass die Branches A und B. Dadurch ist die Entwicklung eines Features getrennt von der Hauptline. Idealerweise arbeitet jeder Entwickler auf seinem eigenen Branch. Der Entwickler kann ungestört an dem Feature arbeiten ohne dass er einen bestehenden Build zerstört. Wurde ein Feature fertig implementiert und getestet, wird der zugehörige Branch in den master-Branch gemerged. Wenn jeder Entwickler an seinem eigenen Branch arbeitet, können diese auch räumlich getrennt arbeiten, da sie sich nicht beim Bearbeiten derselben Datei in die Quere kommen. 


#### Gitflow
Als nächste Strategie stellen wir GitFlow vor. 
Gitflow wirkt auf den ersten Blick im Gegensatz zu der vorherigen Branching Strategie sehr komplex. Es passt das Feature Branching an agile Vorgehensweisen an, der typische dynamische Workflow wie zum Beispiel bei SCRUM wird mit Gitflow unterstützt. Durch die Struktur der Branches wird der Management-Overhead erheblich reduziert. 
Im Gegensatz zum Feature Branching bleibt den Entwicklern allerdings weniger Freiraum bei der Umsetzung.
Wie bei den vorherigen Strategien befinden sich auf dem Master nur stabile und fertige Versionen des Projektes. Der Hotfix Branch dient zur Implementierung kleiner dringender Änderungen und zur Fehlerbehebung.
Die eigentliche Entwicklung passiert in den Feature-Branches, im Beispiel Feature 1 und Feature 2. Sobald ein Feature fertig implementiert wurde, wird es in den Devleop-Branch gemerged um Merge-Konflikte mit anderen Features zu bereinigen. Ist die Entwicklung komplett abgeschlossen wird der Develop-Branch in den Release-Branch integriert, um danach in den Master-Branch aufgenommen zu werden. Dies ist besonderst hilfreich bei iterativen Vorgehensweise, wenn etwa wöchentliche Releases veröffentlicht werden. Wird ein Fehler gefunden, kann der Entwickler schnell eine bestimmte Version auschecken, um zu überprüfen an welcher Stelle der Bug einprogrammiert wurde. 

### Merging
Der Begriff Merging wurde bereits mehrmals im Video erwähnt, es handelt sich dabei um das Zusammenführen von zwei Branches. Beim Merging wird also die bisherige Version des Projekts mit einer neueren überschrieben, wobei die alten Stände selbstverständlich im Repository erhalten bleiben. Das bedeutet dass die komplette Projekthistorie gespeichert und abrufbar ist. Merge-Konflikte entstehen, wenn in zwei Branches Änderungen an der selben Datei vorgenommen wurden. Hierbei übernimmt git nicht etwa einfach die zeitlich gesehen neuere Version, sondern frägt explizit den Entwickler, welche Version er übernehmen möchte.
GIT unterstützt den Entwickler beim Merging durch eine Vergleich geänderter Dateien mit ihren Änderungen aus beiden Branches. Merge-Konflikte sind in einer verteilten Arbeitsweise unerwünscht und kosten Zeit um sie zu Beheben. Um Konflikte beim Mergen zu vermeiden, muss die Softwarearchitektur an die Arbeitsweise angepasst werden.

### Implikationen für Softwarearchitektur
Die verteilte Arbeitsweise mit Git ist gut mit den Prinzipien der objektorientierten Programmierung vereinbar. Die Grundlagen der Objektorientierung wie Kapselung und Modularität sind genau die Merkmale, die ein Team braucht, welches mit Git arbeitet. Werden die Merkmale möglichst gut umgesetzt, sind sie eine große Hilfe um wenige Merge-Konflikte zu erzeugen.
Aufgaben verschiedener Entwickler können beim objektorientierten Programmieren auf verschiedene Objekte verteilt werden. Wenn jeder Entwickler nur an einem Objekt arbeitet, können quasi keine Merge-Konflikte entstehen. 
Dadurch treten Merge Konflikte nur noch an Stellen auf, an denen Module zusammengeführt werden, wie zum Beispiel Interfaces.

### Dokumentationsmöglichkeiten in Git
Um in großen, kollaborativen Software-Projekten den Überblick über Veränderungen zwischen Commits und Features der Software zu behalten, ist eine vollständige Dokumentation unerlässlich.
Git unterstützt das, indem es den Entwickler dazu auffordert, zu jedem Commit eine Commit-Nachricht zu verfassen. Wenn diese Commit-Messages konsequent sinnvoll formuliert sind, wird dadurch schon eine leicht nachvollziehbare Dokumentation über Änderungen und Implementierungen erstellt.
Außerdem bieten viele gängige Git-Plattformen wie Github oder Gitlab Unterstützung für Textformatierung in Markdown-Notation. Markdown vereinfacht das erstellen von leicht darstellbaren Readmes, Changelogs und ähnlichem.

### Fazit
Letzlich ist zu Sagen, dass GIT für eine effektive verteilte Software entwicklung unabdingbar ist. Wenn wir uns an ein paar Grundregeln zur Arbeitsweise mit GIT halten, kann der Entwicklungsprozess nahezu reibungslos ablaufen. Wichtig sind aussagekräftige Commit-Messages, denn durch diese wird fast automatisch eine kleine Dokumentation über unser Projekt erstellt. Modularität unseres Codes ist ebenfalls ein wichtiges Grundprinzip, denn die Vermeidung von Merge-Konflikten beschleunigt die Entwicklung maßgeblich. Schließlich ist es noch hilfreich, wenn wir je nach Vorgehensmodell eine sinnvolle Branching-Strategie wählen, nach welcher wir unser Projekt entwickeln.



