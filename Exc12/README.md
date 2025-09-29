# Exponierung der Draft Möglichkeit in den ODATA UI Service

**Achtung: Ab dieser Stelle funktioniert unser EARLY_NUMBERING nicht mehr.  
Mit Draft kann es nur in Unmanaged-Szenarien verwendet werden.  
Dazu müssen die Save-Methode etc. aber auch implementiert werden**  

**Umstellung Datenmodell**  
  - Änderung des Typs für TravelID auf sysuuid_x16
  - Umsetzung über Quickfix (Tabelle leeren)
  - Änderung der Klassse zur Befüllung auf die Methode cl_system_uuid=>create_uuid_x16_static( )
  - Prüfe im Data Preview
  - Entferne das Early_Numbering aus der Behavior Definition
  - Erweitere das Feld TravelID auf numbering : managed
  - Löschen und neu anlegen der Draft Tabelle

**Draft Handling in der Fiori Elements App**  
  - Anpassung der Behavior Projection mittels use draft;
  - Explizit exponierung der 5 Draft Actionts
  - Im Preview einen neuen Flug anlegen, alles leer lassen und ohne Create oder Cancel in die Liste zurückkehren
  - Inhalt der Draft-Tabelle prüfen

