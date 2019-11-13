# TonUINO_Fork-Affenbox
Own TonUINO Fork
Mein eigener Fork der TonUINO DEV 2.1
- Start Up Sound und ShutDown Sound eingefügt.
- Zu-/Abschalten des Lautsprechers über Pin 8
- Ergänzung einer Zellspannungsmessung über einen Spannungsteiler, inkl. Ausgabe des Ladezustands über eine RGB LED
      Update: Damit einzelne falsche Messwerte nicht direkt zum ausschalten führen, wurde ein Counter eingebaut, der erst nach 10     aufeinanderfolgende Messwerten     die nächste Schwelle übernimmt 
- Ergänzung Ausschalten über langen druck auf Pause Taste
- Zellspannungsmessung ist jetzt über ein defien zu/abwählbar
- Serielle Ausgaben können über ein #define zu/abgeschaltete werden (27% Speicherersparnis ohne Ausgaben)
- beschleunigter setup() durch anpassung der Reihenfolge und entferen des 2sec Delays nach der initialisierung des DFPlayers

Neues Feature: Puzzle Spiel

Ein simples Spiel für den TonUINO, dass zwei zueinander gehörende Karten erwartet.
Ihr müsst dafür auch ein paar MP3s in eurem mp3 Ordner auf der SD-Karte ergänzen. Diese könnt ihr hier herunter laden.

Funktion:
1. Als erstes müsst Ihr die Modifikationskarte "Puzzlespiel" über das Admin Menü erstellen.

2. Danach müsst ihr zwei Puzzleteile über die Normale Kartenkonfiguration erstellen. 
Hierbei wählt ihr wie gewohnt den Ordner in dem eure MP3s für das Spiel liegen.
Wählt nun den Modus Puzzle, der letzte Menüpunkt.
Jetzt wählt ihr das MP3.
Zum Schluss müsst ihr dem Puzzleteil eine Nummer geben. Teile mit gleicher Nummer gehören zusammen. Die beiden Teile MÜSSEN aber mindestens unterschiedliche MP3s haben oder in verschieden Ordnern liegen!

Die Puzzleteile können im Normalen Betrieb wie ein Einzeltrack abgespielt werden.

3. Aktiviert das Spiel durch Auflegen der Modifikationskarte.

4. Jetzt seit Ihr im Spiel. 
Das Spiel akzeptiert nur zum Spiel gehörende Karten alle anderen Karten werden mit einem Signalton abgelehnt.
Ihr könnt nun ein beliebiges Puzzleteil auflegen, und das MP3 dazu wird abgespielt. Anschließend kann folgendes passieren:
- Ihr legt ein Puzzleteil mit der gleichen Nummer auf (ausgenommen das gerade aufgelgte) und bekommt ein bestätigendes Signal. Teil gefunden! Jetzt kann man ein neues Teil auflegen und weiter spielen.
- Ihr legt ein Teil mit einer anderen Nummer auf. Ein Fehlerton ertönt und Ihr müsst weiter nach dem richtigen Teil suchen.
- Ihr haltet den Up & Down Button gleichzeitig gedrückt und last ihn nach ca 1s los. Das aktuell gespeicherte Teil wird gelöscht und man kann eine neue Runde starten.
- Ihr könnt den Pausetaster drücken und hört die letzte Ausgabe erneut oder stoppt eine laufende Ausgabe

5. Das Spiel wird durch erneutes Auflegen der Modifikationskarte beendet.





# TonUINO
Die DIY Musikbox (nicht nur) für Kinder


# Change Log

## Version 2.1 (xx.xx.xxxx) noch WIP
- Partymodus hat nun eine Queue -> jedes Lied kommt nur genau 1x vorkommt
- Neue Wiedergabe-Modi "Spezialmodus Von-Bis" - Hörspiel, Album und Party -> erlaubt z.B. verschiedene Alben in einem Ordner zu haben und je mit einer Karte zu verknüpfen
- Admin-Menü
- Maximale, Minimale und Initiale Lautstärke
- Karten werden nun über das Admin-Menü neu konfiguriert
- die Funktion der Lautstärketasten (lauter/leiser oder vor/zurück) kann im Adminmenü vertauscht werden
- Shortcuts können konfiguriert werden!
- Support für 5 Knöpfe hinzugefügt
- Reset der Einstellungen ins Adminmenü verschoben
- Modikationskarten (Sleeptimer, Tastensperre, Stopptanz, KiTa-Modus)
- Admin-Menü kann abgesichert werden

## Version 2.01 (01.11.2018)
- kleiner Fix um die Probleme beim Anlernen von Karten zu reduzieren

## Version 2.0 (26.08.2018)

- Lautstärke wird nun über einen langen Tastendruck geändert
- bei kurzem Tastendruck wird der nächste / vorherige Track abgespielt (je nach Wiedergabemodus nicht verfügbar)
- Während der Wiedergabe wird bei langem Tastendruck auf Play/Pause die Nummer des aktuellen Tracks angesagt
- Neuer Wiedergabemodus: **Einzelmodus**
  Eine Karte kann mit einer einzelnen Datei aus einem Ordner verknüpft werden. Dadurch sind theoretisch 25000 verschiedene Karten für je eine Datei möglich
- Neuer Wiedergabemodus: **Hörbuch-Modus**
  Funktioniert genau wie der Album-Modus. Zusätzlich wir der Fortschritt im EEPROM des Arduinos gespeichert und beim nächsten mal wird bei der jeweils letzten Datei neu gestartet. Leider kann nur der Track, nicht die Stelle im Track gespeichert werden
- Um mehr als 100 Karten zu unterstützen wird die Konfiguration der Karten nicht mehr im EEPROM gespeichert sondern direkt auf den Karten - die Karte muss daher beim Anlernen aufgelegt bleiben!
- Durch einen langen Druck auf Play/Pause kann **eine Karte neu konfiguriert** werden
- In den Auswahldialogen kann durch langen Druck auf die Lautstärketasten jeweils um 10 Ordner oder Dateien vor und zurück gesprungen werden
- Reset des MP3 Moduls beim Start entfernt - war nicht nötig und hat "Krach" gemacht
