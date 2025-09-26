# RAP Business Object und OData UI Service

- CDS Projektion View ZXX_C_TRAVEL anlegen
    Provider Contract Transactional Query
    Basis ist ZXX_I_TAVEL
    Metadatenerweiterung erlauben
    Suche aktivieren
    Klartextnamen aus den Assoziationen übernehmen

- Metadaten ZXX_C_TRAVEL anlegen
    Layer Customer

- Service Definition ZXX_UI_TRAVEL anlegen, welche ZXX_C_TRAVEL exponiert

- Service Binding ZXX_UI_TRAVEL_O4 für OData V4 anlegen und publizieren
    Test im Preview
- Service Binding ZXX_UI_TRAVEL_O2 für OData V2 anlegen und publizieren
    Test im Preview
=> Einige Funktionen wie Create existieren im V4 nur mit Draft-Tabelle. 
    Für die ersten Tests nehmen wir daher V2

  
