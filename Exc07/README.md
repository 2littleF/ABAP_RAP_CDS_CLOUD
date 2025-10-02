# Input Felder und Wertehilfen

**Direkte Eingaben in Datenfelder ermöglichen, bzw. Felder als Read-Only definieren.**<br>
**CDS Annotationen für Wertehilfen nutzen**<br>
<br>
Direkte Dateneingabe für Update ermöglichen<br>
  - Prüfe in der Behavior Definition von ZXX_I_TRAVEL und ZXX_C_TRAVEL, ob Update erlaubt ist<br>
  - Prüfe, ob im Preview auf Objekt-Ebene der Edit-Button vorhanden ist<br>
  <br>
Setze Eingabefelder auf Read-Only oder Mandatory<br>
  - In der Behavior Definition von ZXX_I_TRAVEL dürfen semantische Key-Felder und Status-Felder nicht editierbar sein<br>
      AgencyID, TravelID und Overallstatus müssen als Ready-Only deklariert werden<br>
      CustomerID, StartDate und EndDate müssen als Mandatory deklariert werden<br>
  - Gehen in den Edit-Modus im Preview, findet ein automatischer Check statt?<br>
<br>
Führe eine Wertehilfe ein (Achtung, evtl. Hard-Reload im Browser erforderlich)<br>
  - Im Projection View ZXX_C_TRAVEL wird ein Wertehilfe für die CustomerID benötigt<br>
  - Nutze die Annotation @Consumption.valueHelpDefinition<br>
  - Die Wertehilfe /DMO/I_Customer kann dafür genutzt werden<br>
  - Gibt es Besonderheiten bei der Wertehilfe, um die Validierung der Eingaben zu steuern?<br>
  https://help.sap.com/docs/ABAP_PLATFORM_NEW/fc4c71aa50014fd1b43721701471913d/0addf879b42e4aa2824f630803ccbdfa.html?locale=en-US<br>



    

