# Dynamische Action und Feldkontrolle  

**Action ein- und ausschalten bzw. Änderungen von Feldern ein- und aussschalten**  

**Action SET_TO_CANCELLED für Sätze im Status Storniert aussschalten**  
  - Instanz Feature-Control für die Action in der Behavior Definition ZXX_I_TRAVEL einschalten  <br>
  - Methode hinzufügen  <br>
  - Lese die Sätze mit READ ENTITY und bilde eine Loop-Schleife  <br>
  - Füge für jeden Satz eine Zeile zu RESULT hinzu mit korrespondierenden Schlüssel %tky  <br>
  - Wenn der Status Storniert ist, oder das Endedatum in der Vergangenheit liegt (nutze CL_ABAP_CONTEXT_INFO), wird die Funktion deaktiviert  <br>
    Sonst aktiviert  <br>
    Nutze hierzu die Konstanten der Struktur if_abap_behv=>fc-  <br>
    Fülle damit im Result die Struktur %features  <br>
  - Test im Preview<br>

**Operation Update ausschalten**  
  - Für die Sätze, wo SET_TO_CANCELLED deaktiviert wurde, darf zusätzlich kein Update mehr erfolgen<br>
  - Erweitere in der Behavior Definition den Update mit einer Instanz Feature Control<br>
  - Erweitere die Loop-Schleife<br>
  - Test im Preview<br>

**Führe eine Feldkontrolle ein**  
  - Das Startdatum und die CustomerID sollen über eine Instanz Feature Control laufen<br>
  - Das EndDate bleibt mandatory<br>
  - Wenn das Startdatum kleiner gleich heute ist, dürfe die Felder nicht mehr geändert werden<br>
    Ansonsten sind sie mandatory<br>
  - Erweitere dazu die Loop-Schleife mit den Prüfungen<br>
  - Test im Preview  <br>

