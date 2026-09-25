# Indkøbsliste

## Formål

Denne indkøbsliste beskriver **hvilke typer dele** der skal bruges til første version af Jakobs drone, og **hvilke specifikationer** der skal kontrolleres før køb. Listen undgår bevidst at låse projektet fast på ubekræftede produktmodeller, priser eller lagerstatus.

## Indkøbsramme

- Konkrete køb skal så vidt muligt ske gennem **europæiske salgssteder**.
- Producenter og produktserier må gerne undersøges bredt, men de bør først skrives ind som kandidater, når de kan skaffes gennem relevante europæiske forhandlere.
- **iFlight** kan undersøges som en mulig producent til for eksempel frame eller elektronik, men er i denne fase kun en **mulig kandidat** og ikke et fast valg.
- **FPV24** kan undersøges som et muligt **europæisk salgssted**, men er endnu ikke valgt som endelig leverandør.

## Bekræftede projektkrav

- 5-tommer quadcopter
- INAV som softwareplatform
- GPS og Return to Home
- Ingen FPV i version 1
- 4S LiPo i første version
- 4-i-1 ESC med **3-6S understøttelse** for fremtidig fleksibilitet

## Nødvendige dele

### 1. 5-tommer frame

**Krav**

- beregnet til 5-tommer propeller
- plads til passende flight-controller/ESC-stack
- rimelig plads til GPS, receiver og kabelføring

**Hvorfor den er nødvendig**

Frame er den mekaniske base, som holder motorer, elektronik og batteri samlet.

### 2. Fire børsteløse motorer

**Krav**

- 4 ens motorer til quadcopter
- egnet til 5-tommer propeller
- specifikationer der passer til planlagt 4S-drift
- motorvalg skal ikke blokere for, at ESC'en senere kan bruges i et 6S-scenarie

**Hvorfor de er nødvendige**

Motorerne skaber løft og styring. De skal passe til propeller, totalvægt og den spænding, dronen flyves på.

### 3. 4-i-1 ESC med 3-6S understøttelse

**Krav**

- 4-i-1 ESC
- understøttelse af **3-6S**
- strømkapacitet med passende sikkerhedsmargin i forhold til motorer og propeller

**Hvorfor den er nødvendig**

ESC'en styrer motorerne og er central for strømforsyning og driftssikkerhed. 3-6S-kravet gør det muligt at starte på 4S og stadig bevare mulighed for senere opgradering.

### 4. INAV-kompatibel flight controller

**Krav**

- dokumenteret understøttelse i officiel INAV-version
- tilstrækkelige UART-porte til mindst GPS og receiver
- fysisk størrelse der passer til frame/stack
- relevant sensor- og strømtilslutning til projektets behov

**Hvorfor den er nødvendig**

Flight controlleren kører INAV og samler data fra sensorer, radio og GPS, så dronen kan stabiliseres og styres.

### 5. GPS-modul

**Krav**

- kompatibelt med flight controller og INAV
- egnet til montering med friest mulig udsigt mod himlen

**Hvorfor det er nødvendigt**

GPS er nødvendig for navigation, position og Return to Home.

### 6. Receiver og sender

**Krav**

- receiver der understøtter en protokol, som flight controlleren kan bruge
- sender til line-of-sight styring
- nok kanaler til arming, modes og eventuel RTH-funktion

**Hvorfor de er nødvendige**

Uden radiosystem kan piloten ikke styre dronen sikkert eller vælge relevante flyvetilstande.

### 7. 4S LiPo-batteri

**Krav**

- 4S LiPo til første version
- størrelse og vægt der passer til frame og ønsket flyveprofil
- afladningskapacitet der matcher drone og propeller

**Hvorfor det er nødvendigt**

Batteriet leverer energi til hele systemet. 4S er valgt som den første og bekræftede driftsform.

### 8. Propeller

**Krav**

- størrelse passende til 5-tommer frame
- korrekt rotationsretning og hulmål til motorerne
- egnet til valgt motor- og spændingssetup

**Hvorfor de er nødvendige**

Propeller omsætter motorkraft til løft og styring.

### 9. XT60 og strømledninger

**Krav**

- batteristik og ledninger dimensioneret til den forventede strøm
- loddekvalitet og trækaflastning skal kunne håndtere vibrationer

**Hvorfor det er nødvendigt**

Strømforbindelsen mellem batteri og elektronik skal være robust og elektrisk sikker.

### 10. Kondensator

**Krav**

- monteres efter ESC-producentens anbefalinger
- spændingsrating skal passe til systemet

**Hvorfor den er nødvendig**

En kondensator kan dæmpe elektrisk støj og hjælpe med at beskytte elektronikken mod spændingsspidser.

### 11. Buzzer

**Krav**

- kompatibel med flight controllerens buzzer-udgang

**Hvorfor den er nødvendig**

En buzzer gør det nemmere at finde dronen efter landing eller fejl og kan bruges som sikkerheds- og statusindikator.

### 12. Lader til LiPo

**Krav**

- egnet til 4S LiPo
- understøtter balanceladning

**Hvorfor den er nødvendig**

LiPo-batterier skal oplades korrekt og kontrolleret for at være sikre.

### 13. Værktøj

**Krav**

- passende værktøj til montering, lodning og kontrol

**Hvorfor det er nødvendigt**

Samling og fejlfinding kræver de rigtige værktøjer, ellers øges risikoen for fejl og skader på komponenter.

### 14. Sikkerhedsudstyr

**Krav**

- udstyr til sikker håndtering af LiPo og lodning

**Hvorfor det er nødvendigt**

Projektet involverer både varme værktøjer og energitætte batterier, som kræver sikker arbejdspraksis.

## Anbefalede dele og materialer

Følgende er ikke altid absolut nødvendige for at tænde systemet, men de er stærkt anbefalede:

- ekstra propeller til test og udskiftning
- batteristropper og skridsikkert underlag til batteriet
- krympeflex og kabelstyring
- multimeter til spændings- og kontinuitetskontrol
- røgstopper eller strømbegrænset første-opstartsmetode
- reserveskruer, afstandsstykker og bløde monteringsdele hvis nødvendigt

## Valgfrie ting til senere

Disse ting er **ikke del af version 1**, men kan overvejes senere:

- ekstra batterier til længere testdage
- transportkasse til udstyr
- reservemotor eller ekstra arme til reparation
- logbog eller måleskema til flyvetest

> **Bemærk:** FPV-udstyr er bevidst ikke med i denne første BOM.

## Kompatibilitetskontrol før køb

Før dele bestilles, skal følgende kontrolleres:

### Spænding

- Kan flight controller, ESC og eventuelle regulatorer bruges i det planlagte 4S-setup?
- Er ESC'en tydeligt specificeret til **3-6S**, så fremtidig opgradering er mulig?

### Strøm og belastning

- Kan ESC'ens strømrating håndtere den forventede belastning fra motorer og propeller?
- Passer batteriets afladningskapacitet til resten af systemet?

### Motor KV og propeller

- Er motorernes KV passende til 5-tommer propeller og 4S?
- Er kombinationen forsvarlig, hvis man senere vil arbejde videre mod 6S?

### UART-tilgængelighed

- Har flight controlleren nok ledige UARTs til GPS og receiver?
- Er der stadig plads til nødvendig signalering og fremtidige behov?

### GPS-understøttelse

- Understøtter flight controller og INAV det planlagte GPS-setup?
- Er der fysisk og elektrisk kompatibilitet?

### Receiverprotokol

- Matcher receiverens protokol flight controllerens indgange og INAV-opsætning?
- Er der nok kanaler til arm, flyvetilstande og RTH-relaterede funktioner?

### Fysisk stack-størrelse

- Passer flight controller og ESC fysisk i frame?
- Er der plads til kabler, kondensator, GPS og batterimontering uden at presse dele sammen?

### Salgssted og support

- Kan delen købes fra et **europæisk salgssted** med tydelige specifikationer?
- Er det let at finde datablad, mål, strømdata og returinformation?
- Hvis en del fra for eksempel **iFlight** overvejes, er kompatibiliteten så verificeret, og findes den via en relevant europæisk forhandler?
