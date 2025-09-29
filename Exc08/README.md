# Eingabeprüfung über Validierung

**Verhinderung der Speicherung von ungültigen Werten**
  - Entferne den Zusatz useForValidation: true in ZXX_C_TRAVEL für die Kundennummer, falls vorhanden
    Die Prüfung soll jetzt über Coding erfolgen und nicht über die Wertehilfe

**Prüfe die Kundennummer in der Behavior Definition und Implementation**  
  - Lege in der Behavior Definition ZXX_I_TRAVEL eine Validation für das Feld CustomerID mit dem Namen ValidateCustomer für on save an  
  - Erzeuge die Methode mit Quickfix  
  - Nutze READ ENTITY oder READ ENTITIES um die relevanten Travel einzulesen    
  - Falls die CustomerID nicht vorhanden ist, erzeuge eine Instanz der Fehlerklasse ZCM_XX_TRAVEL mit SEVERITY = ERROR  
    Erweitere hierzu die Nachrichtenklasse ZMESSAGES_XX aus der vorherigen Übung um eine sinnvolle Nachricht  
    Erweitere die Ausnahmeklasse ZCM_XX_TRAVEL um eine zusätzliche Struktur-Konstante  
    Füge die Nachricht und den Schlüssel zu Response-Parameter REPORTED-TRAVELXX  
    Markiere dabei im Element die Customer-ID %element = VALUE #( custmerid = if_abap_behv=>mk-on )  
    Füge den Travel zum Failed-Parameter FAILED-TRAVELXX hinzu (Corresponding zu TRAVEL)  
  - Prüfe den Preview, ob die Prüfung funktioniert  

**Prüfe das Startdatum des Travels**  
  3 Validationen einbauen  
  - 1. Prüfung: Das Startdatum darf nicht in der Vergangenheit oder leer sein  
  - 2. Prüfung: Das Endedatum darf nicht in der Vergangenheit oder leer sein   
  - 3. Prüfung: Das Endedatum muss nach dem Startdatum liegen  
