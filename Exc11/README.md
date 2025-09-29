# Draft Handling für RAP Business Object  

**Unterstützung von Entwürfen im RAP ermöglichen**  

**Draft Changes durch zusätzlichen Zeitstempel**  
  - Erweiterung der Datenbanktabelle um ein zusätzliches Zeitstempel Feld loc_changed_at
  - Erweiterung des Root CDS ZXX_I_TRAVEL um das Feld mit passender Annotation localInstanceLastChangedAt
  - Erweiteurng Projektionsview ZXX_C_TRAVEL um das neue Feld
  - Erweiterung der UI Metadaten um das neue Feld mit Annotation hidden
  - Prüfe den Preview, das alles noch funktioniert

**Draft Handling im RAP Business Objekt übernehmen**  
  - Füge in der Behavior Definition von ZXX_I_TRAVEL das Statement with draft; ein  
  - Füge eine draft table ein und erzeuge sie mit einem Quickfix
  - Prüfe die Definition der neuen Tabelle
  - Füge das Feldmapping in die Behavior Definition ein
  - Füge zum lock master die Ergänzung total etag hinzu und das Feld für die lokale Änderungszeit
    Der lock master total etag (Lockkriterieum über das gesamte BO für Drafts ist das letzte Änderungsdatum) wird zu Lastchangedat  
    Der etag master (deklariert die Master Entität für Locks) ist das neue Feld mit dem lokalen Zeitstempel  
  - Deklariere die Draft Actions Edit, Activate, Discard, Resume
  - Deklariere die Draft Determine Action Prepare
    
