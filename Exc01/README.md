# CDS Datenmodel anlegen

**Tabellen anlegen**<br>
  - Lege die Tabellen aus dem Tabellen-Verzeichnis an.<br>
  - Vorlage sind die entsprechenden /DMO/-Tabellen (keine Änderungen auf dem Original)  <br>
    /DMO/TRAVEL => ZDMOTRAVEL_XX  <br>
    /DMO/OALL_STAT => ZDMOOALL_STAT_XX  <br>
    /DMO/OALL_STAT_T => ZDMOOALLSTAT_TXX  <br>
  <br>
**Klasse zxx_rap_fill_zdmo_tables zur Befüllung anlegen**<br>
  Befülle die Tabellen für Travel und Status mit den Daten aus den Original-Tabellen  <br>
  Für den Overall-Status gilt das Mapping  <br>
            CASE travel~status    "[N(New) | P(Planned) | B(Booked) | X(Cancelled)]  <br>
              WHEN 'N' THEN 'O'  <br>
              WHEN 'P' THEN 'O'  <br>
              WHEN 'B' THEN 'A'  <br>
              ELSE 'X'  <br>
            END    <br>
  Füge in die Text-Tabelle für die Sprache Deutsch (oder die Anmeldesprache) entsprechende Texte ein  <br>
  <br>
**Befüllung in der Konsole ausführen**<br>
<br>
**Views für die Wertehilfe für den OVerall-Status anlegen**  <br>
  ZXX_I_OVERALL_STATUS_VH analog zu /DMO/I_OVERALL_STATUS_VH  <br>
  ZXX_I_OVERALL_STATUS_VH_TEXT analog zu /DMO/I_OVERALL_STATUS_VH_TEXT  <br>
<br>
**Root-View anlegen ZXX_I_TRAVEL**  <br>
  Legen einen Root-View (Normaler CDS mit Zusatz ROOT) für die Reisen an  <br>
  Der Root-View hat Assoziationen und entsprechende Pfad-Exponierung zu  <br>
  /DMO/I_Agency            as _Agency  <br>
  /DMO/I_Customer          as _Customer  <br>
  ZXX_I_OVERALL_STATUS_VH as _OverallStatus  <br>
  I_Currency               as _Currency  <br>
  <br>
**Data Preview ausführen**<br>
  
