# Datenbank

## HSQLDB

HSQLDB ist ein einfaches Datenbanksystem. Es erlaubt nur eine Verbindung, kann also nur zu Testzwecken genutzt werden. Anpassungen zum Schema und zu Beispieldaten in der Datei `db.script`.

## Verbindungsdaten

- **URL:** `jdbc:hsqldb:hsql://localhost:9010/pizza`
- **Username:** `sa`
- **Password:** *(leer)*

## Schema

(hier evtl. das Schema beschreiben?)

##  Anleitung

Hier findest Du die wichtigsten Schritte bei der Arbeit mit der Datenbank.

### Starten der DB

Zum Starten führe folgenden Befehl im Ordner `db` aus:

```bash
java -cp ./hsqldb.jar org.hsqldb.Server -database.0 file:db -dbname.0 pizza -port 9010
```

Zum Stoppen der DB:
In der Bash `strg + c`.

### Ändern der Inhalte

Um das Schema der Datenbank zu ändern, muss man die Datei `**db.script**` bearbeiten. **Achtung:** Keine Leerzeilen oder Zeilenumbrüche in einer Anweisung!

### Neuaufbau der DB

Um eine Datenbank neu aufzubauen, gehe wie folgt vor:

1. Stoppe die Datenbank, falls diese läuft.
1. Lösche die Dateien, die durch das Ausführen der `start_db_as_server.sh` Datei erstellt werden. (`db.log`, `db.lck` und den Ordner `db.tmp`)
1. Passe das Datenbank-Script an.
1. Starte die Datenbank erneut.

### Zugriff per Eclipse

Mit Eclipse können die Datenbankinhalte gesichtet werden. Jedoch kann nur eine Verbindung offen sein - also entweder vom Programm, oder vom Eclipse.

1. Perspective "Database Development" öffnen
1. "Connection Profile" mit den Verbindungsdaten erstellen - das Treiber-JAR (`hsqldb.jar`) muss explizit mit absoluter Pfadangabe aus dem `db`-Ordner ausgewählt werden.

### Zugriff per Intellij

Mit Intellij können Datenbanken gesichtet werden und Statements abgeschickt werden. Hiezu muss eine aktive Verbindung bestehen.

1. Rechts den Reiter Datenbank aufklappen.
2. Auf das + drücken und unter Data Source `HSQLDB` auswählen.
3. Unter `Path` den phad in den db/ ordner des Projektes angeben.
4. Unter `URL` den Path nach `jdbc:hsqldb:file:` anhängen und am ende des Path noch einmal `/db` anhängen.
5. Login Felder befüllen. s.o.

### Hinweis

Bei einer Intellij Datenbankverbindung kann es zu Fehlernkommen wenn der Liberty gestartet ist.
Auch wenn Intellij eine Aktive DB Verbindung hat ist `Test-Connection` nicht mehr möglich!


 

 

 

 

 

 

 

​            	              