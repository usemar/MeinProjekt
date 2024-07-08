
<h1>Dokumentation
<h4> Einrichten des Repository auf github.com

- login auf www.github.com mit username und passwort
- Durch Klick auf "+" in der rechten oberen Ecke erscheint das Menü mit der Option "New Repository"...
- Nach Auwahl "New Repository" wird ein neues Fenster angezeigt bei dem folgende Angaben nötig waren:
- Name für Repository im Feld "Repository name" angeben
- Klick auf "Create Repository"

<h4>Einrichten des SSH Schlüssels 

- Ausführung folgender Befehle
- ssh-keygen -t rsa -b 4096 -C "meine.Emailadresse"
- vergabe des verlangten "passwortes"

<h4>Klonen von MeinProjekt auf Github in mein Verzeichnis auf dem Client
- Terminalbefehl: git clone git@github.com:usemar/MeinProjekt.git

<h4>Konfigurieren von Git
- Terminalbefehl: git config user.name "meinname"
-     ""        : git config user.email "meineemail"

<h4>Initialen Commit hinzufügen
- Terminalbefehl: git  add main.py
- Terminalbefehl: git commit -m "Haupdatei aktualisiert"
<h4>Feature Branch hinzufügen und Datei im Unterverzeichnis "util"  hinzufügen

- Terminalbefehl: git checkout -b feature
- Terminalbefehl: git add utils/database.py
- Terminalbefehl: git commit -m "Neue Funktion hinzugefügt"
- Wechsel zurück in den Branch master
- Terminalbefehl: git checkout master
- Bearbeite die Datei "main.py" und führe einen Commit auf dem "master"-Branch durch:
- Terminalbefehl: echo "Bearbeitung der Maindatei" >> main.py
- Terminalbefehl: git add main.py
- Terminalbefehl: git commit -m "Hauptdatei aktualisiert"

<h4>Den "feature" Branch in den "main" Branch mergen
- Terminalbefehl: git merge feature
- Ergebnis: feature wurde automatisch über "Merge made by the 'recursive' strategy" gemerged

<h4>Recursive Merge-Strategie in GitHub

- Die "Recursive Merge"-Strategie ist eine Standard-Merge-Strategie in GitHub, die verwendet wird, um zwei Branches zusammenzuführen. Diese Strategie funktioniert, indem sie rekursiv auf die Struktur der Commits und deren Bäume zugreift.
- Wenn Git auf Konflikte stößt, versucht es, diese automatisch zu lösen, indem es die Änderungen aus beiden Branches kombiniert. Wenn es Konflikte gibt, die nicht automatisch aufgelöst werden können, markiert Git diese Stellen im Code und der Entwickler muss die Konflikte manuell beheben.
- Die "Recursive Merge"-Strategie hat einige besondere Merkmale:

- Drei-Wege-Merge: Git verwendet einen Drei-Wege-Merge-Algorithmus, der den gemeinsamen Vorfahren (common ancestor) der beiden zu merge-enden Branches berücksichtigt. Dadurch kann Git besser nachvollziehen, wie sich der Code in beiden Branches verändert hat.
- Automatische Konfliktlösung: Git versucht, Änderungen, die unabhängig voneinander gemacht wurden, automatisch zu integrieren. Bei Konflikten, die nicht automatisch aufgelöst werden können, wird der Entwickler zur manuellen Konfliktlösung aufgefordert.
- Subtree-Merges: Wenn Git erkennt, dass ein Verzeichnis aus einem der Branches in einen anderen verschoben wurde, kann es die Inhalte dieser Verzeichnisse korrekt mergen.

Diese Strategie wird häufig verwendet, da sie sehr effektiv bei der Integration von Änderungen aus verschiedenen Branches ist und viele Konflikte automatisch löst.