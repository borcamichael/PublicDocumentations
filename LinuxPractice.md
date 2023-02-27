Linux-Administration Übung:
- Erstelle eine virtuelle Maschine (mit VirtualBox oder QEMU)
- Übertrage dein public key auf der virtuellen Maschine, um ssh ohne Passwort nutzen zu können
- Verbinde dich mit der virtuellen Maschine per SSH
- Kopiere eine Datei host -> guest und umgekehrt

Bash-Skript Übung:
- Schreibe ein Bash-Skript, das alle Informationen (CPU, Arbeitsspeicher, Festplatten, IP usw.) über deinen PC/Laptop findet und übersichtlich darstellt.
- Schreibe ein Bash-Skript, das automatisch 10 Dateien auf deinem host erstellt und sie anschließend auf der virtuellen Maschine kopiert.
- Erstelle eine txt-Datei, die folgendes enthält:
```
Person A, Sales, 45000
Person B, Marketing, 55000
Person C, IT, 75000
```
- Teil 1: Schreibe ein Bash-Skript, das die Namen der Mitarbeiter und ihre Gehälter ausgibt. Der Ausgabebereich soll wie folgt aussehen:
```
Person A, 45000
Person B, 55000
Person C, 75000
```
- Teil 2: Füge im selben Bash-Skript Code hinzu, der die Mitarbeiter findet, die ein Gehalt von über 50000 haben. Der Ausgabebereich soll wie folgt aussehen:
```
Person B, 55000
Person C, 75000
```
