# Behavior für das Composite RAP BO

**Operationen, Determinations und Validations für das Child Entity**  

**Operationen Create Update Delete**  
  - Füge in der Behavior Defintion von Booking in ZXX_I_TRAVEL die Operationen Update und Delete ein  
  - Was passiert, wenn Create eingeführt werden soll?  
  - Füge das Create in der Assoziation zur Child Entity ein
  - Mache die neuen Operationen in der Behavior Projection ZXX_C_TRAVEL bekannt
  - Prüfe im Preview, ob die neuen Buttons zur Verfügung stehen

**Determination für den semantischen Schlüssel der Child Entity**  
  - Definiere eine Determination determineSemanticKey für CustomerID und TravelUUID aus der Root-Entity.  
    Und der BookingID über die höchste Nummer (oder Festwert (eigentlich über einen Nummernkreis))
  - Wenn CustomerID oder TravelUUID leer ist, lese sie per READ ENTITY aus dem Root
  - Nutze für das Lesen im Composite den Zusatz by \_Pfad
  - Prüfe im Preview
    
