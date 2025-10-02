# RAP Business Object und OData UI Service<br>
<br>
- CDS Projektion View ZXX_C_TRAVEL anlegen<br>
    Provider Contract Transactional Query<br>
    Basis ist ZXX_I_TAVEL<br>
    Metadatenerweiterung erlauben<br>
    Suche aktivieren<br>
    Klartextnamen aus den Assoziationen übernehmen<br>
<br>
- Metadaten ZXX_C_TRAVEL anlegen<br>
    Layer Customer<br>
<br>
- Service Definition ZXX_UI_TRAVEL anlegen, welche ZXX_C_TRAVEL exponiert<br>
<br>
- Service Binding ZXX_UI_TRAVEL_O4 für OData V4 anlegen und publizieren<br>
    Test im Preview<br>
- Service Binding ZXX_UI_TRAVEL_O2 für OData V2 anlegen und publizieren<br>
    Test im Preview<br>
=> Einige Funktionen wie Create existieren im V4 nur mit Draft-Tabelle. <br>
    Für die ersten Tests nehmen wir daher V2<br>

  
