# Nummernvergabe und Determination

**Für den Create von Travel wird die interne Nummervergabe über das RAP Framework aktiviert  <br>
und über eine Determination wird die Konsistenz der semantischen Schlüssel sichergestellt**  <br>
<br>
**Anlegen von Travel prüfen**  
  - Prüfe, dass Behavior Definition und Behavior Projection das Anlegen per Create erlauben  <br>
  - Lege einen Travel an und prüfe ihn im Data Preview  <br>
    Gibt es Felder mit initialen Werten?  <br>
    Sind die Felder für Änderungen initial?   <br>
    Was passiert, wenn noch ein Travel angelegt werden soll?  <br>
<br>
**Aktiviere die interne Nummerierung**  
  - Aktiviere die Nummerierung in der Behavior Definition von ZXX_I_TRAVEL,  <br>
  TravelID soll nur Read-Only sein und intern nummeriert werden  <br>
  Warum geht field ( readonly, numbering : managed ) TravelID; nicht?  <br>
  - Erweitere die Behavior Definition um eine interne Early Numbering  <br>
  Lege die Methode an, ein Nummernkreis braucht nicht beachtet werden, ziehe die nächsthöhere freie ID  <br>
  Prüfe dazu die Signatur der Methode mit F2, übergeben wird eine Liste mit Travels, für die eine ID benötigt wird  <br>
  Mach eine Loop-Schleife um sicher zu stellen, dass nur Sätze ohne ID verarbeitet werden  <br>
  Sätze mit Travel-ID werden bereits hier an MAPPED-TRAVELXX übergeben  <br>
  Alle anderen Sätze werden bekommen eine neue TravelID und werden MAPPED-TRAVELXX hinzugefügt.   <br>
  Dabei werden die Felder %CID und %KEY übergeben  <br>
  - Erweitere die bisherigen Validierungen, damit sie auch bei Create greifen  <br>
  Was passiert, wenn jetzt im Preview ein neuer Travel angelegt werden soll?  <br>
  Prüfe den Ablauf auch im Debugger, insbesonder die %-Felder  <br>
<br>
**Determination für semantische Key-Felder**  
  - Setze die AgencyID in Abhängigkeit vom User  <br>
    In unserem Beispiel ermitteln wir die Agency nicht, sondern setzen einen Festwert.  <br>
    Füge in die Behavior Defintion von ZXX_I_TRAVEL eine neue Determination determineSemanticKey on modify { create; } ein <br>
    Nutze in der Methode einen Tabellentyp FOR UPDATE zxx_i_travel  <br>
    Ordne die Schlüssel der ITAB zu über lt_travel_upd = CORRESPONDING #( keys ) zu  <br>
    Füge über ein Feldsymbol die Travel-Agency hinzu (Änderungsfelder sind leer, weil nur Create beachtet wird)  <br>
    Führe die MODIFIY ENTITY durch  <br>
    Alle Einträge, wo Du der letzte Änderer bist, sollten jetzt die Agency haben<br>
<br>
**Setze Create-Informationen** 
  - Es fehlen noch das Createby und Createat  <br>
    Setze es über Semantische Annotationen in Root-CDS ZXX_I_TRAVEL<br>

    
    
