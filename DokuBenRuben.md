# Projekt SWEN – GIT zur verteilten Software Entwicklung

## 1. Branching
### 1.1 Branching Strategien
automatische Dokumentation durch Commit-Messages
#### Release Branching
Für jeden Release einer Software wird zu Beginn ein neuer Branch angelegt. Dieser wird erst fertiggestellt und dann wieder auf den Master gemerged
![Release Branching example image](data:image/png;base64,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)


#### Feature Branching
Für jedes Feature einer Software wird ein Branch erstellt, erst bei Fertigstellung wird mit der Mainline gemerged.
![Feature Branching example image](https://wac-cdn.atlassian.com/dam/jcr:9b77665b-ee56-4e8c-a5f1-33388bcc9f93/cicd-basic-workflow.png?cdnVersion=1386)


### Gitflow
Verbindung von Release und Feature-Branching

- **Master:** nur fertige und stabile Versionen
- **Hotfix:** eigener Branch für jeden Hotfix; nach Fertigstellung Integration in Devlop- und Master-Branch
- **Release:** Ist eine Entwicklung abgeschlossen, so werden die Änderungen vom Dev-Branch zuerst in den Release-Branch integriert, dort wenn nötig noch einige Änderungen vorgenommen und dann in den Master-Branch integriert.
- **Develop:** Auflösung von Merge-Konflikten
- **Feature I & II:** Eigentlich Entwicklung findet hier statt

![Girflow example image](https://i.stack.imgur.com/F00b8.png)


### Merging
Problem vorher: Zwei Entwickler arbeiten gleichzeitig an denselben Dateien, der Entwickler der zuerst sein Code hochlädt, dem sein Code wird vom nächsten überschrieben. Dadurch werden nur die Änderungen vom zweiten Entwickler gespeichert

Ziel: Beibehalten aller Änderungen an einem Projekt, nach dem mehrere Entwickler gleichzeitig an einer Stelle gearbeitet haben.

Beim Mergen muss man sich für eine der beiden Lösung entscheiden

**GIT**
- Merkt sich den Ausgangszustand eines Branch
- Beim Mergen zeigt GIT, welche Dateien und genau welche Zeilen in den beiden Branches geändert wurden