# Projektplan

## Formål

Denne projektplan er lavet til et skoleprojekt om at planlægge og bygge en open source 5-tommer drone med INAV, GPS og Return to Home.

## Overordnede læringsmål

Eleven skal arbejde med:

- teknisk planlægning
- læsning af specifikationer og kompatibilitet
- mekanisk samling
- grundlæggende lodning og ledningsforståelse
- softwareopsætning i INAV
- sikker brug af LiPo og værktøj
- test, fejlfinding og dokumentation

## Fase 1: Projektforståelse og krav

### Mål

- forstå projektets formål
- afklare faste designvalg
- afgrænse version 1

### Leverancer

- opdateret README
- oversigt over projektkrav

### Acceptkriterier

- det fremgår tydeligt, at projektet er en 5-tommer drone
- det fremgår tydeligt, at version 1 er uden FPV
- det fremgår tydeligt, at projektet bruger INAV, GPS, RTH og 4S

## Fase 2: Indkøb og kompatibilitet

### Mål

- forstå hvilke dele der er nødvendige
- kontrollere kompatibilitet før køb

### Leverancer

- indkøbsliste med krav og forklaringer
- kompatibilitetscheckliste

### Acceptkriterier

- alle hovedkategorier af dele er beskrevet
- spænding, strøm, UART, GPS og fysisk pasform er tænkt ind
- dokumentet undgår ubekræftede slutvalg og priser

## Fase 3: Sikkerhed og arbejdsforberedelse

### Mål

- lære sikker håndtering af værktøj, batterier og test

### Leverancer

- sikkerhedsdokument
- aftalte sikkerhedsregler for bygge- og testdag

### Acceptkriterier

- propelsikkerhed er tydeligt beskrevet
- LiPo-håndtering er tydeligt beskrevet
- det fremgår, at RTH ikke erstatter pilotansvar eller regler

## Fase 4: Samling og lodning

### Mål

- samle frame og montere elektronik korrekt
- lære grundlæggende praktisk arbejde med dronekomponenter

### Leverancer

- delvist eller helt samlet drone
- dokumenterede trin i instruktionsmanualen

### Acceptkriterier

- frame, motorer og elektronik kan monteres uden åbenlyse konflikter
- ledningsføring er planlagt fornuftigt
- der er udført kontrol af polaritet og kortslutning før opstart

## Fase 5: Softwareopsætning i INAV

### Mål

- forbinde flight controller til configurator
- opsætte grundlæggende funktioner

### Leverancer

- softwaredokument
- notat om valgt INAV-version og verificeret target

### Acceptkriterier

- board orientation er kontrolleret
- receiver og GPS er konfigureret
- batteriovervågning, failsafe og RTH er gennemgået

## Fase 6: Test og første flyvning

### Mål

- gennemføre sikre bench tests
- udføre en kontrolleret første flyvning

### Leverancer

- tjekliste for pre-flight
- testnoter fra første flyvning

### Acceptkriterier

- bench tests er udført uden propeller
- første flyvning sker i et kontrolleret område
- RTH testes først, når grundlæggende kontrol og GPS er bekræftet

## Forslag til enkel arbejdsgang

- [ ] Læs README og projektkrav
- [ ] Gennemgå indkøbslisten
- [ ] Kontrollér kompatibilitet før køb
- [ ] Læs sikkerhedsregler
- [ ] Saml og lod delene
- [ ] Konfigurér INAV
- [ ] Udfør bench tests uden propeller
- [ ] Gennemfør første flyvning
- [ ] Evaluer og opdatér dokumentationen
