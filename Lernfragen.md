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
