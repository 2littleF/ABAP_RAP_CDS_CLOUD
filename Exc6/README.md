Action definieren und implementieren

Action um eine Reise zu stornieren. Verfügbarmachung der Action über einen Button in Fiori Elements.

Aktiviere den Alias TRAVELXX in den Behavior-Definition für Root und Projektion.

Nachrichtenklasse definieren
- Erzeuge eine Nachrichtenklasse ZMESSAGES_XX mit den Nachrichten
    120 Storno erfolgreich
    130 Bereits storniert

Exception-Klasse ZCM_XX_TRAVEL definieren
- Erbt von CX_STATIC_CHECK
- Implementiert das Interface IF_ABAP_BEHV_MESSAGE
- 2 öffentliche Konstantestrukturen (PUBLIC text eingeben und CTRL+SPACE für TextIdExceptionClass
    Eine Konstante für CANCEL_SUCCESS und eine Konstante für ALREADY_CANCELLED
    Übernehme die Nachrichten aus der Nachrichtenklasse ZMESSAGES_XX
- Füge einen optionalen Parameter SEVERITY zum Constructor hinzu um das Attribut if_abap_behv_message~m_serverity zu füllen
- Lösche die Methode für GET_TEXT

Füge in der Behavior Definition für den Root ZXX_I_TRAVEL eine neue Action SET_TO_CANCELLED hinzu
- Falls noch nicht passiert, erzeuge die Implementierungsklasse ZBP_XX_I_TRAVEL
- Lege die Methode über einen Quick-Fix an
- Lese in der Methode aus dem RAP BO ZXX_I_TRAVEL die Reise(n) aus, um den Status zu prüfen
- Prüfe über eine Schleife, ob der Status bereits Cancelled ist, gebe dann eine Instanz der Exception Class mit severity if_abap_behv_message~severity-error.
  Gib die Nachricht über den Export-Parameter REPORTED zurück mit passenden Schlüssel des Fluges
  Alternativ storniere den Flug über MODIFY ENTITY über eine Update-Tabelle.
  Ist der Update erfolgreich (gs_failed ist initial), erzeuge eine Instanz der Exception Class mit der Text Id CANCEL_SUCCESS und der severity if_abap_behv_message~severity-success.
  Gib die Nachricht wie zuvor zurück.
  

