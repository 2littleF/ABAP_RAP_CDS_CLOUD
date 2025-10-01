# Optimistisches Sperrverhalten implementieren

**Für das Sperrverhalten sollen die administrativen Felder Letzer Änderer und Änderungsdatum gefüllt werden,
wenn eine Datenänderung passiert.**<br>
- Annotiere die Felder im Datenmodel ZXX_I_TRAVEL mit den semantischen Annotationen<br>
    @Semantics.systemDateTime.lastChangedAt: true<br>
    @Semantics.user.lastChangedBy: true<br>
- Lade den Datensatz aus der EML-Übung aus der Tabelle ZDMOTRAVEL_XX in den Data Preview
- Führe die Main-Methode erneut aus
- Prüfe die Änderung im Data Preview

**Definiere das ETag Feld für die Sperrprüfung**
- In der Behavior Definition zu ZXX_I_TRAVEL den ETAG MASTER für das Feld LASTCHANGEDAT aktivieren
- In der Behavior Projektionn die Nutzung des ETag über use etag übernehmen
  

