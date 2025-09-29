# Exponierung der Draft Möglichkeit in den ODATA UI Service

**Achtung: Ab dieser Stelle funktioniert unser EARLY_NUMBERING nicht mehr.  
Mit Draft kann es nur in Unmanaged-Szenarien verwendet werden.  
Dazu müssten die Save-Methode etc. aber auch implementiert werden**  

**Umstellung Datenmodell**  
  - Zusätzliches Feld key travel_uuid : sysuuid_x16 not null;  
  - travel_id ist kein Schlüsselfeld mehr (wird zur Herausforderung bei der Aktivierung)  
  - Umsetzung über Quickfix (Tabelle leeren)  
  - Änderung der Klassse zur Befüllung auf die Methode uuid() für die UUID  
  - Änderung der CDS ZXX_I_TRAVEL und ZXX_C_TRAVEL
  - Prüfe im Data Preview  
  - Entferne das Early_Numbering aus der Behavior Definition  
  - Erweitere das Feld TravelUUID auf numbering : managed
      field ( readonly, numbering : managed ) TravelUUID;  
      field ( readonly ) TravelID, AgencyID, OverallStatus;
  - Nehme das Feld ins Mapping auf  
  - Löschen und neu anlegen der Draft Tabelle  
  - Entfernen des Early Numbering aus der Klasse
  - Ändere die Determination für den Semantischen Key auf eine feste TravelID

**Umstellung auf Authorisierungsprüfung**  
  - Ändere in der Behavior Definition den Authorization Master auf Instanz  
  - Entferne im Create die globale Prüfung  
  - Gehe in die Behavior Implementation und implementiere eine Methode für die Instanzprüfung    

**Draft Handling in der Fiori Elements App**  
  - Anpassung der Behavior Projection mittels use draft;  
  - Explizit Exponierung der 5 Draft Actionts  
  - Im Preview einen neuen Flug anlegen, alles leer lassen und ohne Create oder Cancel in die Liste zurückkehren  
  - Inhalt der Draft-Tabelle prüfen  

**Validierungen an das Draft anpassen**  
  - Nehme die Validierungen in das Prepare auf, damit sie beim Übergang von Draft auf die aktive Version durchlaufen werden  
  - Passe die Validierungen an, damit Nachrichten vom Type State statt dem Type Transition genutzt werden  
  - Füge dabei zu Beginn der Loop-Schleife für die State_Area und den TKY eine leere Zeile an, um den vorherigen Satz zu überschreiben  

**Achtung, Inkonsistenz in der Musterlösung, noch Speicherung von ungültigen Datum möglich**  
