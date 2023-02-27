Linux-Administration Übung:
- Erstelle eine virtuelle Maschine (mit VirtualBox oder QEMU)
  - Selbsterklärend
  - in diesem Beispiel werde ich 2 VMs nutzen (mikesbuntu1 und mikesbuntu2)
- Übertrage dein public key auf der virtuellen Maschine, um ssh ohne Passwort nutzen zu können
  - Vorerst, die Passwort Authentifizierung an lassen
  - Erstelle SSH Keys `ssh-keygen -t rsa` auf beiden Maschinen
  - kopiere den Schlüssel `ssh-copy-id -i ~/.ssh/id_rsa.pub mike@mikesbuntu2` & `ssh-copy-id -i ~/.ssh/id_rsa.pub mike@mikesbuntu1`
  - schalte die Passwort Authentifizierung aus:
    - `sudo nano /etc/ssh/sshd_config`
    - finde `#PasswordAuthentication yes` & ändere es zu `PasswordAuthentication no` !Entferne # sonst bleibt die Zeile als Kommentar
    - `sudo systemctl restart ssh`
- Verbinde dich mit der virtuellen Maschine per SSH
  - `ssh mike@mikesbuntu2` und Passwort des mikesbuntu1 SSH Schlüssels eingeben 
- Kopiere eine Datei host -> guest und umgekehrt
  - `touch testfile`
  - `echo test > testfile`
  - `scp testfile mikesbuntu2:~/`
  - `scp mikesbuntu2:~/testfile testfile2`
  - `cat testfile2` 

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
