# Exponierung der Draft Möglichkeit in den ODATA UI Service

**Achtung: Ab dieser Stelle funktioniert unser EARLY_NUMBERING nicht mehr.  
Mit Draft kann es nur in Unmanaged-Szenarien verwendet werden.  
Dazu müssten die Save-Methode etc. aber auch implementiert werden**  

**Umstellung Datenmodell**  
  - Änderung des Typs für TravelID auf sysuuid_x16  
  - Umsetzung über Quickfix (Tabelle leeren)  
  - Änderung der Klassse zur Befüllung auf die Methode cl_system_uuid=>create_uuid_x16_static( )  
  - Prüfe im Data Preview  
  - Entferne das Early_Numbering aus der Behavior Definition  
  - Erweitere das Feld TravelID auf numbering : managed  
  - Löschen und neu anlegen der Draft Tabelle  
  - Entfernen des Early Numbering aus der Klasse   

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
