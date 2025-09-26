EML in ABAP anwenden

Über diesen Weg kann später ein Brownfield-Ansatz mitgenutzt werden, bzw. 
das Coding für Operationen und Aktionen erfolgen.


- Erzeuge neue Klasse zrap_xx_eml um eine Entität zu lesen und zu ändern
    Lese in der Main-Methode vom Root-Objekt ZXX_I_TRAVEL über Read Entity 
    einen Flug und gib seinen Status über die Konsole aus.
    Nutze die Schlüssel-Komponenten der Struktur.
    
    Baue dazu Strukturen und ITabs für Read Import, Result und Update über ZXX_I_TRAVEL
    Zusätzliche Strukturen für Response for Failed und Response for Reported über ZXX_I_TRAVEL
    
    Erweitere die Methode um ein Update, dass einen neuen Statuswert über Modify Entity Update Fields speichert.

    Debugge das Coding und prüfe die Strukturen der ITabs.
    
  
