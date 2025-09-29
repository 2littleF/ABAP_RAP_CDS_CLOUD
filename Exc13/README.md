# Composite RAP Business Object  

**Hinzufügen von Child-Entities mittel Buchungen**  
- Lege eine Tabelle für Buchungen an mit Berücksichtigung des Draft-Szenarios
- Erweitere die Befüllungs-Klasse auf die Buchungen
- Entwerfe einen neuen CDS ZXX_I_BOOKING
- Verweise per Assoziation und Composition zwischen den Parent und Child
- Prüfe im Data Preview den Absprung in die Buchungen

**Definiere die Komposition in der Behavior Definition**  
  - Füge die Child-Entity zur Behavior Definition ZXX_I_TRAVEL hinzu
    association _Booking { with draft; }
  - Definiere in der gleichen Datei eine neue Behavior für Booking
  - Linke die Child-Entity zur transparenten Tabelle und erzeuge eine Draft Tabelle
  - Aktiviere interne managed Nummerering der BookingUUID
  - Setze Readonly: TravelUUID, BookingID, BookingDate, LocalLastChangedAt
  - Setze Mandatory: CustomerID, AirlineID, ConnectionID, FlightDate, CurrencyCode
  - Mappe den CDS auf die Datenbanktabelle  
