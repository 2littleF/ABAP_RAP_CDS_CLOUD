# Nummernvergabe und Determination

**Für den Create von Travel wird die interne Nummervergabe über das RAP Framework aktiviert  
und über eine Determination wird die Konsistenz der semantischen Schlüssel sichergestellt**  

**Anlegen von Travel prüfen**  
  - Prüfe, dass Behavior Definition und Behavior Projection das Anlegen per Create erlauben  
  - Lege einen Travel an und prüfe ihn im Data Preview  
    Gibt es Felder mit initialen Werten?  
    Sind die Felder für Änderungen initial?   
    Was passiert, wenn noch ein Travel angelegt werden soll?  

**Aktiviere die interne Nummerierung**  
  - Aktiviere die Nummerierung in der Behavior Definition von ZXX_I_TRAVEL,  
  TravelID soll nur Read-Only sein und intern nummeriert werden  
  Warum geht field ( readonly, numbering : managed ) TravelID; nicht?  
  - Erweitere die Behavior Definition um eine interne Early Numbering  
  Lege die Methode an, ein Nummernkreis braucht nicht beachtet werden, ziehe die nächsthöhere freie ID  
  Prüfe dazu die Signatur der Methode mit F2, übergeben wird eine Liste mit Travels, für die eine ID benötigt wird  
  Mach eine Loop-Schleife um sicher zu stellen, dass nur Sätze ohne ID verarbeitet werden  
  Sätze mit Travel-ID werden bereits hier an MAPPED-TRAVELXX übergeben  
  Alle anderen Sätze werden bekommen eine neue TravelID und werden MAPPED-TRAVELXX hinzugefügt.   
  Dabei werden die Felder %CID und %KEY übergeben  
  - Erweitere die bisherigen Validierungen, damit sie auch bei Create greifen  
  Was passiert, wenn jetzt im Preview ein neuer Travel angelegt werden soll?  
  Prüfe den Ablauf auch im Debugger, insbesonder die %-Felder  

**Determination für semantische Key-Felder**  
  - Setze die AgencyID in Abhängigkeit vom User  
    In unserem Beispiel ermitteln wir die Agency nicht, sondern setzen einen Festwert.  
    Füge in die Behavior Defintion von ZXX_I_TRAVEL eine neue Determination determineSemanticKey on modify { create; } ein 
    Nutze in der Methode einen Tabellentyp FOR UPDATE zxx_i_travel  
    Ordne die Schlüssel der ITAB zu über lt_travel_upd = CORRESPONDING #( keys ) zu  
    Füge über ein Feldsymbol die Travel-Agency hinzu (Änderungsfelder sind leer, weil nur Create beachtet wird)  
    Führe die MODIFIY ENTITY durch  
    Alle Einträge, wo Du der letzte Änderer bist, sollten jetzt die Agency haben  
    
