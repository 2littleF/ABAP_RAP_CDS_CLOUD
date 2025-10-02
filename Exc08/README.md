# Eingabeprüfung über Validierung

**Verhinderung der Speicherung von ungültigen Werten**
  - Entferne den Zusatz useForValidation: true in ZXX_C_TRAVEL für die Kundennummer, falls vorhanden<br>
    Die Prüfung soll jetzt über Coding erfolgen und nicht über die Wertehilfe<br>

**Prüfe die Kundennummer in der Behavior Definition und Implementation**  <br>
  - Lege in der Behavior Definition ZXX_I_TRAVEL eine Validation für das Feld CustomerID mit dem Namen ValidateCustomer für on save an  <br>
  - Erzeuge die Methode mit Quickfix  <br>
  - Nutze READ ENTITY oder READ ENTITIES um die relevanten Travel einzulesen    <br>
  - Falls die CustomerID nicht vorhanden ist, erzeuge eine Instanz der Fehlerklasse ZCM_XX_TRAVEL mit SEVERITY = ERROR  <br>
    Erweitere hierzu die Nachrichtenklasse ZMESSAGES_XX aus der vorherigen Übung um eine sinnvolle Nachricht  <br>
    Erweitere die Ausnahmeklasse ZCM_XX_TRAVEL um eine zusätzliche Struktur-Konstante  <br>
    Füge die Nachricht und den Schlüssel zu Response-Parameter REPORTED-TRAVELXX  <br>
    Markiere dabei im Element die Customer-ID %element = VALUE #( custmerid = if_abap_behv=>mk-on )  <br>
    Füge den Travel zum Failed-Parameter FAILED-TRAVELXX hinzu (Corresponding zu TRAVEL)  <br>
  - Prüfe den Preview, ob die Prüfung funktioniert  <br>

**Prüfe das Startdatum des Travels**  <br>
  3 Validationen einbauen  <br>
  - 1. Prüfung: Das Startdatum darf nicht in der Vergangenheit oder leer sein  <br>
  - 2. Prüfung: Das Endedatum darf nicht in der Vergangenheit oder leer sein   <br>
  - 3. Prüfung: Das Endedatum muss nach dem Startdatum liegen  <br>
