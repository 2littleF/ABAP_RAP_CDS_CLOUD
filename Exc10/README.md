# Dynamische Action und Feldkontrolle  

**Action ein- und ausschalten bzw. Änderungen von Feldern ein- und aussschalten**  

**Action SET_TO_CANCELLED für Sätze im Status Storniert aussschalten**  
  - Instanz Feature-Control für die Action in der Behavior Definition ZXX_I_TRAVEL einschalten
  - Methode hinzufügen
  - Lese die Sätze mit READ ENTITY und bilde eine Loop-Schleife
  - Füge für jeden Satz eine Zeile zu RESULT hinzu mit korrespondierenden Schlüssel %tky
  - Wenn der Status Storniert ist, oder das Endedatum in der Vergangenheit liegt (nutze CL_ABAP_CONTEXT_INFO), wird die Funktion deaktiviert  
    Sonst aktiviert  
    Nutze hierzu die Konstanten der Struktur if_abap_behv=>fc-  
    Und aus dem Result die Struktur %features
  - 
