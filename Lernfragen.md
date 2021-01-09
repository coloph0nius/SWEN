# Lernfragen

## Welche Strategie beim Benutzen von Git ermöglicht in Kombination mit dem Konzept der Klassen in der objektorientierten Programmierung die Verhinderung von Merge-Konflikten?

### Zusammenfassung mehrerer Änderungen in Commits
- Falsch. Je mehr Änderungen in einen Commit gepackt werden, desto eher treten Merge-Konflikte auf.

### Feature-Branching
- Richtig. Das Aufteilen der Arbeit anhand von Features, die in ihren eigenen Klassendateien programmiert werden, kann Merge-Konflikte effektiv vermeiden.

### Commit-Nachrichten
- Falsch. Commit-Nachrichten sagen meist nichts darüber aus, an welcher genauen Stelle im Code etwas verändert wurde und können deshalb Merge-Konflikte nicht verhindern.

### Lineares Programmieren auf dem Master-Branch
- Falsch. Vermeidet zwar Merge-Konflikte, braucht aber keine Klassen.




## In welchem Branch findet die Entwicklung statt, wenn Sie nach der Branching-Strategie Gitflow arbeiten?

### Release-Branch
- Falsch. Der Release-Branch dient der Möglichtkeit Bug-fixing oder Ähnliches zu betreiben, bevor dieser dann in den master-Branch gemerged wird.

### master-Branch
- Falsch. Im master-Branch dürfen sich nur stabile und vollständige Versionen des Projektes befinden, deshalb darf in diesem keine Entwicklung betrieben werden.

### Feature-Branch
- Richtig. In den beiden Feature-Branches findet die eigentliche Entwicklung der Software statt.

### Develop-Branch
- Falsch. Der Develop-Branch ist nur zum Mergen der Feature-Branches zuständig, hier sollen gegebenenfalls auftretende Merge-Konflikte behoben werden.

## Ein Branch enthält immer eine Kopie des gesamten Projekts.

### Ja
- Richtig

### Nein, Commits die auf einem anderen Branch gemacht wurden, sind nicht sichtbar
- Falsch. Ein neuer Branch enthält immer die gesamte git-history

### Nein, nur die Commits seit dem letzten Merge sind enthalten
- Falsch. Ein neuer Branch enthält immer die gesamte git-history

### Nein, jeder neue Branch enthält immer den Ursprungszustand des Projekts
- Falsch. Ein neuer Branch enthält immer die gesamte git-history



## Wie finden Änderungen den Weg ins lokale Repository?

### Sie müssen Commited werden.
- Richtig.

### Durch Pushen
- Falsch. Durch Pushen werden Änderungen im lokalen Repository ins Remote-Repository veröffentlicht, nicht ins lokale Repository aufgenommen.

### Änderungen werden schon während des Schreibens durch Git ins Repository aufgenommen.
- Falsch. Git ist kein Hintergrundprozess, der ständig läuft, sondern wird über explizite Befehle gesteuert, die den aktuellen Arbeitsstand verarbeiten.

### Durch den Befehl git add.
- Falsch, weil die Änderungen dadurch nur in die Staging Area aufgenommen werden. Hinzufügen zum Repository erfolgt durch Commiten
