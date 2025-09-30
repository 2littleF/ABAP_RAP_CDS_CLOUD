# Composite UI Service mit RAP

**Die Child Entity aus dem RAP BO im ODATA Service für die Fiori Elements App aufnehmen**  

**Projektionsview für Booking erstellen**  
  - Erstelle einen Projektionsview ZXX_C_BOOKING
  - Verweise im ZXX_C_BOOKING auf _Travel : redirected to parent ZXX_C_TRAVEL  
  - Verweise im ZXX_C_TRAVEL auf _Booking  : redirected to composition child ZXX_C_BOOKING

**Behavior ZXX_C_TRAVEL anpassen**
  - Definiere eine neue Behavior für ZXX_C_BOOKING in der Behavior Definition von Travel
  - Assoziere in beiden Definitionen zwischen Travel und Booking

**Erweitere die Metadatendefinition für die Anzeige**
  - Erweitere die Service Defintion um ein expose für das Booking  
  - Erweitere die UI-Metadaten um ein neues Facet für Booking mit Verweis auf die Child Entity  
      { id:            'Booking',  
      purpose:       #STANDARD,  
      type:          #LINEITEM_REFERENCE,  
      label:         'Booking',  
      position:      20,  
      targetElement: '_Booking'}  
      ]  
  - Da es sich um eine Liste handelt, muss noch eine Metadaten-Erweiterung für ZXX_C_BOOKING angelegt werden
  - Test im Preview  
