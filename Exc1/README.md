# CDS Datenmodel anlegen

**Tabellen anlegen**
  Lege die Tabellen aus dem Tabellen-Verzeichnis an.
  Vorlage sind die entsprechenden /DMO/-Tabellen (keine Änderungen auf dem Original)
  /DMO/TRAVEL => ZDMOTRAVEL_XX
  /DMO/OALL_STAT => ZDMOOALL_STAT_XX
  /DMO/OALL_STAT_T => ZDMOOALLSTAT_TXX
  
**Klasse zxx_rap_fill_zdmo_tables zur Befüllung anlegen**
  Befülle die Tabellen für Travel und Status mit den Daten aus den Original-Tabellen
  Für den Overall-Status gilt das Mapping
            CASE travel~status    "[N(New) | P(Planned) | B(Booked) | X(Cancelled)]
              WHEN 'N' THEN 'O'
              WHEN 'P' THEN 'O'
              WHEN 'B' THEN 'A'
              ELSE 'X'
            END  
  Füge in die Text-Tabelle für die Sprache Deutsch (oder die Anmeldesprache) entsprechende Texte ein
  
**Befüllung in der Konsole ausführen**

**Root-View anlegen ZXX_I_TRAVEL**
  Legen einen Root-View (Normaler CDS mit Zusatz ROOT) für die Reisen an
  Der Root-View hat Assoziationen und entsprechende Pfad-Exponierung zu
  /DMO/I_Agency            as _Agency 
  /DMO/I_Customer          as _Customer
  ZXX_I_OVERALL_STATUS_VH as _OverallStatus
  I_Currency               as _Currency
  
**Data Preview ausführen**
  
