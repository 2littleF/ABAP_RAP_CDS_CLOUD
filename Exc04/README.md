# EML in ABAP anwenden

**Über diesen Weg kann später ein Brownfield-Ansatz mitgenutzt werden, bzw. <br>
das Coding für Operationen und Aktionen erfolgen.**<br>
<br>
- Erzeuge eine, in der Konsole ausführbare Klasse zrap_xx_eml um eine Entität zu lesen und zu ändern  <br>
    Lese in der Main-Methode vom Root-Objekt ZXX_I_TRAVEL über Read Entity  <br>
    einen Flug und gib seinen Status über die Konsole aus.  <br>
    Nutze die Schlüssel-Komponenten der Struktur.  <br>
      <br>
    Baue dazu Strukturen und ITabs für Read Import, Result und Update über ZXX_I_TRAVEL  <br>
    Zusätzliche Strukturen für Response for Failed und Response for Reported über ZXX_I_TRAVEL  <br>
      <br>
    Erweitere die Methode um ein Update, dass einen neuen Statuswert über Modify Entity Update Fields speichert.  <br>
  <br>
    Debugge das Coding und prüfe die Strukturen der ITabs.  <br>
    
  
