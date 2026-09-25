
# Indkøbsliste til Jakobs drone

## Formål

Denne indkøbsliste beskriver de komponenter, der anbefales til første version af Jakobs drone.

Version 1 bygges som en 5-tommer quadcopter med INAV, GPS og Return to Home, men uden FPV-kamera og videosender. Dronen skal i første omgang flyve med 4S LiPo, mens ESC'en vælges med understøttelse af op til 6S for at bevare mulighed for senere opgradering.

Listen indeholder:

- valgte komponenter
- teknisk begrundelse
- kompatibilitetskontrol
- europæiske købssteder
- priser og lagerstatus
- alternativer, hvis en komponent ikke kan leveres
- samlet budget

Pris- og lagergrundlag: Priser og lagerstatus er undersøgt den 25. september 2026. De skal kontrolleres igen umiddelbart før bestilling.

europæiske købssteder, hvor det er praktisk muligt
## Indkøbsramme

- Konkrete køb skal så vidt muligt ske gennem europæiske salgssteder.
- Hovedleverandørerne i denne version er iFlight Europe og FPV24.
- iFlight Europe sender varer fra Østrig.
- FPV24 er en tysk FPV- og modeldroneforhandler.
- Komponenterne er valgt ud fra dokumenterede specifikationer, fysisk kompatibilitet og tilgængelighed hos europæiske forhandlere.
- Priserne er angivet inklusive den moms, der vises på produktsiderne, men uden fragt og eventuelle betalingsgebyrer.
- Batterilevering til Danmark skal kontrolleres særskilt ved checkout.
- Flywoo GOKU F722 Pro V2 55A 30×30 Stack er valgt som samlet flight-controller- og ESC-løsning.
- SpeedyBee F405 V4 BLS 55A-stacken bruges ikke som primær kandidat, fordi producenten viser produktet som udfaset, og flere europæiske butikker viser det som udsolgt eller kun tilgængeligt efter forespørgsel.

## Bekræftede projektkrav

- 5-tommer quadcopter
- INAV som softwareplatform
- GPS
- Return to Home
- ingen FPV i version 1
- 4S LiPo i første version
- 4-i-1 ESC med mindst 3-6S-understøttelse
- radiosystem til line-of-sight-flyvning
- nok radiokanaler til arming, flyvetilstande, buzzer og RTH
- europæiske købssteder, hvor det er praktisk muligt
- mulighed for senere teknisk udbygning

## Valgt systemarkitektur

Den anbefalede version 1 består af:

- iFlight Nazgul XL5 ECO V1.1 5-tommer frame
- Flywoo GOKU F722 Pro V2 55A 30×30 Stack
- fire iFlight XING-E 2207 2450KV-motorer
- TBS M10 GPS/GLONASS eller et alternativt M10 GPS-modul
- RadioMaster RP1 ExpressLRS 2.4 GHz receiver
- RadioMaster Pocket ExpressLRS 2.4 GHz sender
- CNHL Black Series 1500 mAh 4S 130C-batterier
- Gemfan Hurricane 51433-propeller
- VIFLY Finder 2-buzzer
- SkyRC B6AC Neo LiPo-lader
- TBS Smoke Stopper 2-8S
- ekstern 1000 µF 35 V low-ESR-kondensator
- XT60-pigtail med 12 AWG silikoneledning

## Nødvendige komponenter

### 1. Frame

**Valgt komponent**

iFlight Nazgul XL5 ECO V1.1 Frame Kit

Se iFlight Nazgul XL5 ECO V1.1 Frame Kit

Specifikationer
5-tommer freestyle-frame
understøtter også 5,1-tommer propeller
245 mm wheelbase
5 mm arme
montage til 30,5 × 30,5 mm stack
montage til 20 × 20 mm stack
16 × 16 mm motorbeslag
maksimal stackhøjde på 22 mm
batteristropper inkluderet
skridsikker batteripude inkluderet
motorledningsbeskyttelse inkluderet
udskiftelige arme

Producenten anbefaler 2207-motorer til framen. Den undersøgte version stod til €80,90 og havde 15 enheder på lager.

Hvorfor den er valgt

Framen passer direkte til den valgte 30,5 × 30,5 mm flight-controller/ESC-stack og til motorernes 16 × 16 mm monteringsmønster.

Den giver plads til:

flight controller
ESC
receiver
GPS
kondensator
buzzer
XT60-ledning
kabelføring

Framen er en relativt robust 5-tommer konstruktion, men den er forholdsvis tung. Det er acceptabelt til den første robuste prototype, hvor enkel montage og holdbarhed prioriteres over lavest mulig vægt.

### 2. Motorer

**Valgt komponent**

4 × iFlight XING-E 2207 2450KV

Se iFlight XING-E 2207 2450KV-motor

Specifikationer
2207 statorstørrelse
2450KV
16 × 16 mm M3-montage
4 mm motoraksel
150 mm 20 AWG-motorledninger
oplyst maksimal kortvarig strøm på 35,22 A
egnet til 5-tommer 4S-opbygning

Prisen var €14,90 pr. motor, og produktet stod som klar til afsendelse. Fire motorer koster derfor €59,60.

Hvorfor de er valgt

2450KV ligger i det normale område for en 5-tommer drone på 4S. Motorerne passer fysisk til framen og giver god margin i forhold til ESC'ens 55 A pr. kanal.

Vigtig begrænsning

Motorerne vælges specifikt til 4S-versionen.

Selv om ESC'en understøtter op til 6S, bør man ved en senere normal 6S-opgradering skifte til motorer med lavere KV, typisk omkring 1700 til 1900KV til en 5-tommer opbygning.

ESC'en kan derfor genbruges ved en senere 6S-opgradering, men motorerne bør ikke betragtes som det permanente 6S-valg.

### 3. FC + ESC-stack

**Valgt komponent**

Flywoo GOKU F722 Pro V2 55A 30×30 Stack

Se Flywoo GOKU F722 Pro V2 55A 30×30 Stack hos FPV24

Specifikationer
STM32F722 processor
ICM42688 gyro
30,5 × 30,5 mm montage
4-i-1 ESC med 55 A pr. kanal
separat flight controller og ESC leveres som ét sæt

Produktet stod til €89,90 hos FPV24. Genbestilling var angivet til 4. oktober 2026.

Hvorfor den er valgt

Stacken passer mekanisk til framens 30,5 × 30,5 mm montage og samler flight controller og ESC i én købs- og kompatibilitetsenhed. ESC'ens 55 A pr. kanal giver fortsat god margin i forhold til motorernes oplyste maksimale kortvarige strøm på 35,22 A.

Kontrol før bestilling

- Bekræft aktuel INAV-understøttelse og firmwaretarget i INAV Configurator.
- Bekræft tilgængelige UARTs og konkrete pads til ExpressLRS-receiver, GPS og buzzer i producentens pinout.
- Bekræft ESC'ens spændingsområde, pakkens strømledning og leveringsindhold på den konkrete produktside.

Selv om iFlight eksplicit angiver INAV-understøttelse, skal den konkrete firmwaretarget kontrolleres i den aktuelle INAV Configurator før den endelige bestilling og igen før flashing.

### 5. GPS

**Primært valg**

TBS M10 GPS/GLONASS

Se TBS M10 GPS/GLONASS

Specifikationer
M10 GPS/GLONASS
5 V forsyning
seriel forbindelse
18 × 18 × 6,1 mm
vægt 4,9 g
kabelsæt inkluderet
konfigurerbar baudrate
oplyst standardbaudrate på 38400 bps

Prisen var €18,90. Den konkrete produktside angav genbestilling med forventet tilgængelighed den 5. oktober 2026.

Alternativt valg

Hvis TBS M10 GPS/GLONASS ikke er tilgængeligt ved bestilling, kan et af følgende M10-moduler vælges:

Flywoo GOKU GM10 Nano V3.1 GPS, vist til €21,90
GEPRC GEP M10 GPS, vist til €21,90
iFlight FPV BLITZ M10 QMC5883L GPS Compass V2, vist til €34,90

Se GPS-alternativer hos FPV24

FPV24s tilbehørsoversigt viste disse M10-baserede GPS-moduler blandt de tilgængelige GPS-kandidater.

Valg mellem GPS med og uden kompas

Det primære TBS M10 GPS/GLONASS er valgt som et enkelt GPS-modul.

Et GPS-modul med kompas kan være relevant, men kompasset skal placeres så langt som praktisk muligt fra:

batterikabler
ESC
motorledninger
kraftige strømsløjfer

For første version er et enkelt M10 GPS-modul tilstrækkeligt til den planlagte GPS- og RTH-funktion, forudsat at den aktuelle INAV-konfiguration understøtter den ønskede funktion.

Montering

GPS-modulet skal monteres:

højt eller bagest på framen
med bedst mulig udsigt mod himlen
væk fra ESC og kraftige strømledninger
med mekanisk beskyttelse
med korrekt orientering, hvis der vælges en model med kompas

Der skal muligvis bruges en separat TPU-holder.

### 6. Receiver

**Valgt komponent**

RadioMaster RP1 ExpressLRS 2.4 GHz Nano Receiver

Se RadioMaster RP1 ExpressLRS-receiver

Specifikationer
ExpressLRS 2,4 GHz
CRSF-interface
5 V forsyning
ekstern T-antenne
vægt 2,2 g inklusive antenne
13 × 11 × 3 mm
firmwareopdatering via Wi-Fi
U.FL-antennetilslutning

Prisen var €24,90, og produktet stod som klar til afsendelse.

Tilslutning

Receiveren forbindes til en fuld UART:

5 V
GND
receiver TX til flight controller RX
receiver RX til flight controller TX

I INAV vælges seriel receiver og CRSF-protokol.

Hvorfor den er valgt

ExpressLRS giver:

nok kanaler til projektet
lav receiver-vægt
fleksibel kanalopsætning
mulighed for firmwareopdatering
samme radiosystem i sender og receiver
### 7. Sender

**Valgt komponent**

RadioMaster Pocket ExpressLRS 2.4 GHz

Se RadioMaster Pocket ExpressLRS-sender

Specifikationer
indbygget ExpressLRS 2,4 GHz
EdgeTX
op til 16 kanaler
Hall-effect sticks
USB-C-opladning
foldbar antenne
aftagelige stick-ender
bruger to 18650-celler

Prisen var €86,90. To 18650-celler medfølger ikke og skal købes separat.

Foreslået kanalfordeling
kanal 1: roll
kanal 2: pitch
kanal 3: throttle
kanal 4: yaw
kanal 5: arm
kanal 6: flyvetilstand
kanal 7: Return to Home
kanal 8: buzzer
kanal 9 eller højere: reserveret til senere funktioner

Den endelige kanalfordeling skal tilpasses den valgte EdgeTX- og INAV-konfiguration.

### 8. Batteri

**Valgt komponent**

CNHL Black Series V2.0 1500 mAh 4S 130C XT60

Se CNHL Black Series 1500 mAh 4S-batteri

Specifikationer
4S
14,8 V nominel spænding
1500 mAh
130C oplyst kontinuerlig afladning
XT60-hovedstik
JST/XH-balancestik
12 AWG-ledning
mål 36 × 33 × 76 mm
vægt 174 g

Prisen var €20,90 pr. batteri, og produktet stod som klar til afsendelse.

Anbefalet antal

Der anbefales to batterier til første version.

Ét batteri er teknisk nok til at teste systemet, men to batterier giver bedre mulighed for:

opsætning
testflyvning
genafprøvning efter ændringer
sammenligning af flyvetid og temperatur
Leveringskontrol

LiPo-batteriers fragt til Danmark skal kontrolleres ved checkout hos forhandleren.

### 9. Propeller

**Valgt komponent**

Gemfan Hurricane 51433 Durable Freestyle

Se Gemfan Hurricane 51433-propeller

Specifikationer
diameter 5,1 tommer
pitch 3,5 tommer
tre blade
5 mm centerhul
polycarbonat
to CW og to CCW pr. sæt
anbefalet motorstørrelse 220x til 230x

Prisen blev vist fra €2,99 pr. sæt. Den direkte variant var markeret som ikke længere tilgængelig, men FPV24-kataloget viste andre 51433-varianter fra €2,99.

Anbefalet antal

Der anbefales mindst tre sæt:

ét sæt til første montage
to reservesæt

Fem sæt kan være hensigtsmæssigt, hvis Jakob er ny dronepilot.

Alternativ

Hvis 51433 ikke kan leveres, skal der vælges en anden 5 eller 5,1-tommer propeller med:

M5-centerhul
to CW og to CCW
moderat pitch
egnethed til 2207-motorer og 4S
### 10. XT60 og strømledning

**Valgt specifikation**
ægte XT60-stik
cirka 8 til 10 cm silikoneledning
12 AWG
mekanisk trækaflastning
isolering med krympeflex
placering, hvor ledningen ikke kan ramme propellerne
Kontrol før køb

Det skal kontrolleres, om Flywoo-stacken leveres med en batteriledning med monteret XT60-stik.

Hvis et komplet XT60-pigtail ikke medfølger, skal det købes separat.

### 11. Kondensator

**Valgt specifikation**
1000 µF
35 V
low-ESR
monteres direkte ved ESC'ens plus- og minus-batteripads
ben isoleres med krympeflex
polariteten skal kontrolleres nøje
Hvorfor 35 V vælges

Et fuldt opladet 6S LiPo-batteri når 25,2 V. En kondensator med 35 V-rating giver derfor nødvendig spændingsmargin ved en senere 6S-opgradering.

En 25 V-kondensator må ikke vælges, hvis systemet senere skal kunne anvendes på 6S.

Lagerstatus

En ekstern kondensator er ikke bekræftet i leveringsomfanget for Flywoo-stacken. Den skal derfor stå som en separat BOM-linje, indtil pakkens faktiske indhold er bekræftet.

### 12. Buzzer

**Valgt komponent**

VIFLY Finder 2

Se VIFLY Finder 2-buzzer

Specifikationer
eget internt 80 mAh LiPo-batteri
lydstyrke op til 110 dB
oplyst driftstid op til 30 timer
vægt 5 g
størrelse 24 × 13 × 16 mm
lysføler

Prisen var €15,50, og produktet stod med mere end 10 enheder på lager.

Hvorfor den er valgt

Buzzeren kan fortsætte med at afgive lyd, hvis hovedbatteriet frakobles ved et styrt. Det gør den mere anvendelig end en helt passiv buzzer.

Den forbindes til flight controllerens buzzer-udgang efter producentens diagram.

### 13. LiPo-lader

**Valgt komponent**

SkyRC B6AC Neo

Se SkyRC B6AC Neo-lader

Specifikationer
understøtter 1-6S LiPo
balanceladning
op til 60 W via indbygget AC-forsyning
op til 200 W ved ekstern DC-forsyning
USB-C/PD-understøttelse
indbygget balancer
XT60-tilslutning
netkabel inkluderet

Prisen var €67,90, og produktet stod med fire enheder på lager.

Hvorfor den er valgt

Laderen kan tilsluttes direkte til 230 V via det medfølgende netkabel. Det gør den enklere til første projekt end en ren DC-lader, der kræver separat strømforsyning.

Alternativ

SkyRC B6neo 2 stod til €40,90 og understøtter 1-6S LiPo, men kræver en passende ekstern DC- eller USB-C PD-forsyning.

Til en første opsætning anbefales derfor SkyRC B6AC Neo.

### 14. Smoke stopper

**Valgt komponent**

TBS Smoke Stopper 2-8S

Se TBS Smoke Stopper hos FPV24

FPV24 viste smoke stopperen til €7,49.

Hvorfor den er nødvendig

Smoke stopperen bruges ved første strømtilslutning efter:

lodning af ESC
montage af XT60
installation af flight controller
ændring af strømforbindelser
reparation

Den kan begrænse konsekvenserne af en kortslutning eller forkert forbindelse.

Alternativ

VIFLY ShortSaver V2 med XT30 og XT60 blev vist til €15,90.

## Værktøj

Følgende værktøj anbefales:

temperaturreguleret loddekolbe på cirka 60 til 100 W
passende loddespids til store ESC-pads
elektronikloddetin
fluxpen eller egnet elektronikflux
loddesugefletning
multimeter
pincet
sidebidetang
afisoleringstang
1,5 mm unbrakonøgle
2,0 mm unbrakonøgle
2,5 mm unbrakonøgle
M5-propnøgle
lille skruetrækkersæt
krympeflex i flere størrelser
varmepistol eller anden kontrolleret varmekilde
kabelbindere
dobbeltklæbende skumtape
gevindlås egnet til metal-mod-metal-forbindelser
computer med USB og INAV Configurator
passende USB-kabel til flight controlleren
## Sikkerhedsudstyr

Følgende sikkerhedsudstyr anbefales:

sikkerhedsbriller
varmebestandigt arbejdsunderlag
LiPo-sikkerhedstaske eller egnet brandsikker opbevaringsløsning
ikke-brændbart område til opladning
smoke stopper
multimeter
ventilation ved lodning
mulighed for sikker håndtering af et beskadiget LiPo-batteri
tydelig adskillelse mellem propeller og elektrisk test

Vigtigt: Propellerne må ikke monteres under den første elektriske opsætning, firmwareinstallation, motortest eller receiverkonfiguration.

## Anbefalede dele og materialer

Følgende bør medtages i første indkøb, hvis de ikke allerede findes:

tre til fem sæt propeller
to batterier
to passende 18650-celler til senderen
GPS-holder
ekstra batteristropper
krympeflex
kabelbindere
dobbeltklæbende skumtape
reserveskruer
M3-nylonmøtrikker
bløde stack-gummibøsninger
ekstra XT60-stik
12 AWG silikoneledning
ekstra 1000 µF 35 V low-ESR-kondensator
propelmøtrikker, hvis de ikke medfølger motorerne
LiPo-sikkerhedstaske
brandsikkert opbevaringssted
microSD-kort, hvis flight controllerens logfunktion skal bruges
## Samlet købsliste

| Kategori | Valgt komponent | Antal | Stykpris | Samlet pris | Butik | Status |
|---|---|---:|---:|---:|---|---|
| Frame | iFlight Nazgul XL5 ECO V1.1 | 1 | €80,90 | €80,90 | iFlight Europe | 15 på lager ved kontrol |
| FC + ESC-stack | Flywoo GOKU F722 Pro V2 55A 30×30 Stack | 1 | €89,90 | €89,90 | FPV24 | Genbestilling angivet til 4. oktober 2026 |
| Motorer | iFlight XING-E 2207 2450KV | 4 | €14,90 | €59,60 | FPV24 | Klar til afsendelse ved kontrol |
| GPS | TBS M10 GPS/GLONASS | 1 | €18,90 | €18,90 | FPV24 | Genbestilling angivet til 5. oktober 2026 |
| Receiver | RadioMaster RP1 ELRS 2.4 GHz | 1 | €24,90 | €24,90 | FPV24 | Klar til afsendelse ved kontrol |
| Sender | RadioMaster Pocket ELRS | 1 | €86,90 | €86,90 | FPV24 | Kontrolleres før bestilling |
| Batteri | CNHL Black Series 1500 mAh 4S 130C | 2 | €20,90 | €41,80 | FPV24 | Mere end 10 ved kontrol |
| Propeller | Gemfan Hurricane 51433 | 3 sæt | €2,99 | €8,97 | FPV24 | Variant skal vælges |
| Buzzer | VIFLY Finder 2 | 1 | €15,50 | €15,50 | FPV24 | Mere end 10 ved kontrol |
| Lader | SkyRC B6AC Neo | 1 | €67,90 | €67,90 | FPV24 | Fire på lager ved kontrol |
| Smoke stopper | TBS Smoke Stopper 2-8S | 1 | €7,49 | €7,49 | FPV24 | Vist i katalog |
| Kondensator | 1000 µF 35 V low-ESR | 1 | TBD | TBD | Ikke valgt | Skal tilføjes |
| XT60-pigtail | XT60 med 12 AWG ledning | 1 | TBD | TBD | Ikke valgt | Kontroller ESC-pakken |
| Senderbatterier | 18650-celler | 2 | TBD | TBD | Ikke valgt | Ikke inkluderet med sender |
| GPS-holder | TPU-holder til valgt GPS | 1 | TBD | TBD | Ikke valgt | Afhænger af GPS |
| LiPo-opbevaring | Sikkerhedstaske eller anden egnet løsning | 1 | TBD | TBD | Ikke valgt | Skal tilføjes |

De tekniske data, priser og viste lagerstatus for de valgte hovedkomponenter fremgår af de respektive produktsider.

## Produktlinks samlet

### iFlight Europe
iFlight Nazgul XL5 ECO V1.1 Frame Kit
### FPV24
Flywoo GOKU F722 Pro V2 55A 30×30 Stack
iFlight XING-E 2207 2450KV-motor
TBS M10 GPS/GLONASS
RadioMaster RP1 ExpressLRS-receiver
RadioMaster Pocket ExpressLRS-sender
CNHL Black Series 1500 mAh 4S-batteri
Gemfan Hurricane 51433-propeller
VIFLY Finder 2-buzzer
SkyRC B6AC Neo-lader
TBS Smoke Stopper og øvrigt TBS-tilbehør
Alternative M10 GPS-moduler
## Samlet pris

### Bekræftede komponenter

| Gruppe | Pris |
|---|---:|
| Frame, FC + ESC-stack, motorer, GPS, receiver, buzzer og propeller | €298,57 |
| Sender, to batterier og lader | €196,60 |
| Smoke stopper | €7,49 |
| **Samlet kendt produktpris** | **€502,66** |

### Vejledende pris i danske kroner

Med et rent budgetestimat på 7,46 DKK pr. euro:

€502,66 × 7,46 = cirka 3.750 DKK

Dette er kun et vejledende budgettal. Den faktiske valutakurs afhænger af betalingskort og købstidspunkt.

### Ikke indeholdt i den kendte pris
fragt fra iFlight Europe
fragt fra FPV24
eventuelle valutagebyrer
to 18650-celler
ekstern 1000 µF 35 V kondensator
eventuel separat XT60-pigtail
GPS-holder
LiPo-sikkerhedstaske eller anden egnet opbevaring
eventuelt værktøj
forbrugsmaterialer
eventuelle reservedele
### Realistisk samlet budget

Et realistisk budget for hele første version inklusive mindre el-dele, senderbatterier, sikkerhedsudstyr og fragt er:

cirka 4.300 til 4.700 DKK

Dette er et budgetoverslag og ikke en garanteret forhandlerpris.

## Kompatibilitetskontrol

### Spænding

| Kontrol | Resultat |
|---|---|
| Flight controller og 4S | Godkendt |
| ESC og 4S | Godkendt |
| ESC og senere 6S | Godkendt, ESC understøtter 2-6S |
| Kondensator til 6S | Skal være mindst 35 V |
| Receiverforsyning | 5 V fra flight controller |
| GPS-forsyning | 5 V |
| Buzzerforsyning | Tilsluttes efter flight-controllerdiagrammet |

### Strøm og belastning
Motorernes oplyste maksimale kortvarige strøm er 35,22 A.
ESC'en er specificeret til 55 A kontinuerligt pr. kanal.
ESC'en er specificeret til 65 A burst.
Batteriet bruger XT60 og 12 AWG-ledning.
Den præcise strøm skal verificeres under test via current sensor og flyvelogs.
Motor- og ESC-temperatur skal kontrolleres efter korte første flyvninger.

På baggrund af de offentliggjorte ratings har ESC'en en god nominel margin i forhold til motorernes offentliggjorte kortvarige strøm.

### Motor KV og propeller
2450KV er valgt til 4S.
Motorerne passer fysisk til framen.
Propellerne har M5-centerhul.
Propellerne er anbefalet til motorstørrelser i 220x-230x-området.
Propellerne har moderat pitch til første test.
Ved overgang til 6S skal motorerne som udgangspunkt skiftes til lavere KV.
ESC, flight controller og 35 V kondensator kan bevares ved en senere 6S-opgradering.
### UART-tilgængelighed

Flight controlleren har seks UARTs.

Foreslået fordeling:

UART	FunktionUART 1	Reserveret til eventuel senere FPV
UART 2	ExpressLRS-receiver
UART 3	GPS
UART 4	Ledig eller fremtidig sensor
UART 5	Ledig eller fremtidig sensor
UART 6	ESC-telemetri, hvis anvendt

iFlight angiver UART 2 til receiver, UART 3/4/5 til GPS eller andre sensorer og UART 6 til ESC-telemetri som foreslået ledningsfordeling.

### GPS-understøttelse
GPS-modulet bruger 5 V.
GPS-data sendes via en seriel UART.
Flight controlleren har flere egnede UARTs.
GPS-modulet skal monteres med fri udsigt mod himlen.
RTH må først aktiveres efter korrekt INAV-konfiguration og gennemført funktionskontrol.
GPS-lock, home position, failsafe og flyveretning skal verificeres før første RTH-test.
### Receiverprotokol
RadioMaster RP1 bruger CRSF.
Receiveren kræver en fuld UART.
Senderen og receiveren bruger begge ExpressLRS 2,4 GHz.
Radiosystemet understøtter flere kanaler end projektet kræver.
Der er kanaler nok til arm, flyvetilstande, RTH og buzzer.
Firmwareversion og binding phrase skal være kompatible mellem sender og receiver.
### Fysisk kompatibilitet

| Kombination | Resultat |
|---|---|
| Frame og FC | 30,5 × 30,5 mm, kompatibelt |
| Frame og ESC | 30,5 × 30,5 mm, kompatibelt |
| FC og ESC | Leveres som samlet Flywoo-stack med 30,5 × 30,5 mm montage |
| Frame og motorer | 16 × 16 mm, kompatibelt |
| Frame og propeller | 5 og 5,1 tommer understøttet |
| Motorer og propeller | M5-propelaksel og M5-propelhul |
| Batteri og strømstik | XT60 |
| Batteristørrelse og frame | Skal verificeres under fysisk montage |
| GPS og frame | Kræver egnet placering og muligvis TPU-holder |
| Buzzer og frame | Plads og lydåbning skal kontrolleres |

### FC-ESC-forbindelse

Selv om flight controller og ESC leveres som samlet Flywoo-stack, skal producentens ledningsdiagram stadig følges før tilslutning.

Følgende signaler skal kontrolleres én for én:

batterispænding
GND
motor 1
motor 2
motor 3
motor 4
current sensor
ESC-telemetri

Stik eller ledningsfarver må ikke bruges som eneste grundlag for tilslutningen.

### Forberedelse før første strømtilslutning
Monter ESC og flight controller uden propeller.
Kontroller alle lodninger visuelt.
Mål modstand mellem XT60 plus og minus.
Kontroller kondensatorens polaritet.
Kontroller XT60-polaritet.
Kontroller FC-ESC-kablets pin-rækkefølge.
Kontroller, at ingen motorledninger har forbindelse til frame eller GND.
Tilslut flight controlleren via USB først.
Bekræft korrekt INAV-target.
Installer og konfigurer INAV.
Test receiver og kanalretninger.
Test GPS-kommunikation.
Fjern USB.
Tilslut batteriet gennem smoke stopper.
Kontroller for varme komponenter, unormal lugt eller fejl.
Test motorretning uden propeller.
Monter først propeller efter alle elektriske tests.
### Første INAV-kontrol

Før første flyvning skal mindst følgende verificeres:

korrekt board alignment
korrekt accelerometerretning
accelerometerkalibrering
korrekt modeltype, Quad X
korrekt motorplacering
korrekt motorretning
korrekt propellerretning
receiverkanaler bevæger sig korrekt
arm-switch fungerer
failsafe fungerer
buzzer fungerer
GPS-kommunikation fungerer
tilstrækkeligt GPS-fix
home position registreres
barometerdata ser realistiske ud
batterispænding vises korrekt
current sensor kalibreres
RTH-højde og procedure er sat korrekt
RTH aktiveres først efter kontrolleret test
første flyvning foretages på et åbent område
## Valgfrie ting til senere

Følgende er ikke en del af version 1, men kan overvejes senere:

ekstra batterier
reservemotor
ekstra framearme
transportkasse
feltlader eller kraftigere DC-strømforsyning
kompas
telemetrilogning
mere avanceret GPS
FPV-kamera
videosender
antenne
videoskærm eller goggles
6S-batterier
lavere-KV-motorer til 6S
logbog eller måleskema til flyvetest

> **Bemærk:** FPV-udstyr er bevidst ikke medtaget i denne første BOM.

## Endelig anbefaling

Den anbefalede første version er teknisk sammenhængende:

iFlight Nazgul XL5 ECO V1.1 giver en robust 5-tommer platform.
Flywoo GOKU F722 Pro V2 55A-stacken passer til 30,5 × 30,5 mm-framen og giver 55 A pr. motor. INAV-target og UART-fordeling skal bekræftes før bestilling.
iFlight XING-E 2207 2450KV passer til den valgte 4S-version.
RadioMaster Pocket og RadioMaster RP1 giver et sammenhængende ExpressLRS-radiosystem.
M10 GPS giver grundlaget for position, home position og RTH.
Den selvforsynede VIFLY Finder 2 gør dronen lettere at finde efter et styrt.
SkyRC B6AC Neo giver balanceladning direkte fra 230 V.
Smoke stopper, multimeter og 35 V-kondensator skal behandles som obligatoriske sikkerhedsdele.

Den kendte produktpris er cirka €502,66, svarende til cirka 3.750 DKK før fragt og småmaterialer. Et praktisk samlet budget er omkring 4.100 til 4.500 DKK.

## Vigtigste ændringer i forhold til den oprindelige liste
Generiske produktgrupper er erstattet med konkrete komponenter.
Den udsolgte iFlight BLITZ-løsning er erstattet med Flywoo GOKU F722 Pro V2 55A 30×30 Stack.
Der er tilføjet direkte produktlinks.
Der er tilføjet priser og dokumenteret lagerstatus.
Der er tilføjet et GPS-alternativ.
Der er tilføjet radio, senderbatterier, lader og smoke stopper.
Der er tilføjet samlet pris og realistisk budget.
4S- og 6S-begrænsningerne er gjort tydelige.
FC-ESC-pinout er fremhævet som obligatorisk kontrol.
Kondensatoren er specificeret til 1000 µF og 35 V.
Første elektriske opstart og INAV-kontrol er tilføjet som sikkerhedspunkter.