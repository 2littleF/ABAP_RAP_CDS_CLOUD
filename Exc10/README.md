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
    Fülle damit im Result die Struktur %features  
  - Test im Preview

**Operation Update ausschalten**  
  - Für die Sätze, wo SET_TO_CANCELLED deaktiviert wurde, darf zusätzlich kein Update mehr erfolgen
  - Erweitere in der Behavior Definition den Update mit einer Instanz Feature Control
  - Erweitere die Loop-Schleife
  - Test im Preview

**Führe eine Feldkontrolle ein**  
  - Das Startdatum und die CustomerID sollen über eine Instanz Feature Control laufen
  - Das EndDate bleibt mandatory
  - Wenn das Startdatum kleiner gleich heute ist, dürfe die Felder nicht mehr geändert werden
    Ansonsten sind sie mandatory
  - Erweitere dazu die Loop-Schleife mit den Prüfungen
  - Test im Preview  

