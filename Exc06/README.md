# Action definieren und implementieren

### Action um eine Reise zu stornieren. Verfügbarmachung der Action über einen Button in Fiori Elements.

**Aktiviere den Alias TRAVELXX in den Behavior-Definition für Root und Projektion.**<br>

**Nachrichtenklasse definieren**<br>
- Erzeuge eine Nachrichtenklasse ZMESSAGES_XX mit den Nachrichten<br>
    120 Storno erfolgreich<br>
    130 Bereits storniert<br>

**Exception-Klasse ZCM_XX_TRAVEL definieren**<br>
- Erbt von CX_STATIC_CHECK<br>
- Implementiert das Interface IF_ABAP_BEHV_MESSAGE<br>
- 2 öffentliche Konstantestrukturen (PUBLIC text eingeben und CTRL+SPACE für TextIdExceptionClass<br>
    Eine Konstante für CANCEL_SUCCESS und eine Konstante für ALREADY_CANCELLED<br>
    Übernehme die Nachrichten aus der Nachrichtenklasse ZMESSAGES_XX<br>
- Füge einen optionalen Parameter SEVERITY zum Constructor hinzu um das Attribut if_abap_behv_message~m_serverity zu füllen<br>
- Lösche die Methode für GET_TEXT<br>

**Füge in der Behavior Definition für den Root ZXX_I_TRAVEL eine neue Action SET_TO_CANCELLED hinzu**<br>
- Falls noch nicht passiert, erzeuge die Implementierungsklasse ZBP_XX_I_TRAVEL<br>
- Lege die Methode über einen Quick-Fix an<br>
- Füge action SET_TO_CANCELLED hinzu<br>

**Passe die Methode SET_TO_CANCELLED an. Alle Anpasssungen werden in den Local Types implementiert.**<br>
- Lese in der Methode aus dem RAP BO ZXX_I_TRAVEL die Reise(n) aus, um den Status zu prüfen<br>
- Prüfe über eine Schleife, ob der Status bereits Cancelled ist, gebe dann eine Instanz der Exception Class mit severity if_abap_behv_message~severity-error.<br>
- Gib die Nachricht über den Export-Parameter REPORTED zurück mit passenden Schlüssel des Fluges<br>
- Alternativ storniere den Flug über MODIFY ENTITY über eine Update-Tabelle.<br>
- Ist der Update erfolgreich (gs_failed ist initial), erzeuge eine Instanz der Exception Class mit der Text Id CANCEL_SUCCESS und der severity if_abap_behv_message~severity-success.<br>
  Gib die Nachricht wie zuvor zurück.<br>

**Mache die Action in der Behavior Definition für die Projektion ZXX_C_TRAVEL sichtbar**<br>
- use action SET_TO_CANCELLED;<br>

**Füge den Button in den Metadaten für die UI beim Status hinzu**<br>
- lineItem:       [ { position: 100, importance: #HIGH }, { type: #FOR_ACTION, dataAction: 'set_to_cancelled', label: 'Cancel Travel' } ],<br>
<br>
<br>
Prüfe die Storno-Funktion im Preview, nutze die ID aus der vorherigen Übungen (Coding ermöglich ein Rücksetzen)<br>
Nutze den Debugger, um die Action schrittweise durchzugehenn<br>
*Warum kann der erneute Storno nur nach einem Reload der Daten ausgeführt werden?*<br>

    
                        
  

