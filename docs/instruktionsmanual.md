# Instruktionsmanual

## Formål

Denne manual beskriver en forsigtig og begyndervenlig arbejdsgang til at bygge den første version af Jakobs drone: en 5-tommer quadcopter med INAV, GPS og Return to Home, men **uden FPV**.

> **Sikkerhedsregel:** Propeller skal være **afmonteret under al konfiguration, fejlfinding og bench test**.

## 1. Planlægning

Før samlingen begynder, skal projektets faste krav være forstået:

- 5-tommer frame
- 4S drift i første version
- 4-i-1 ESC med 3-6S understøttelse
- INAV
- GPS og Return to Home
- line-of-sight styring
- ingen FPV i version 1

Bekræft derefter hvilke valg der stadig skal valideres:

- flight controller og INAV-target
- motor/propel-kombination
- receiverprotokol
- fysisk kompatibilitet mellem frame og stack

## 2. Kontrol af dele ved modtagelse

Når delene er ankommet:

- sammenlign dem med indkøbslisten
- kontrollér for transportskader
- kontrollér stik, loddepads og gevind
- læg skruer og små dele i mærkede poser
- bekræft at intet ser bøjet, knækket eller kortsluttet ud

Brug ikke beskadigede LiPo-batterier eller elektronik med tydelige skader.

## 3. Dry fit før endelig montering

Lav først en **tør samling** uden lodning:

- placer frame-delene løst sammen
- læg ESC og flight controller i frame
- kontrollér stakhøjde, hulafstand og kabelføring
- prøv placering af GPS, receiver, buzzer og batteri

Formålet er at opdage pladsproblemer tidligt, før noget loddes fast.

## 4. Samling af frame

- montér frame efter producentens vejledning
- spænd skruer jævnt, men undgå at ødelægge gevind
- kontrollér at intet er skævt eller i spænd

Før elektronik monteres, skal du sikre:

- at armene sidder fast
- at der er plan overflade til stack
- at batteriet senere kan fastgøres sikkert

## 5. Montering af motorer

- montér én motor på hver arm
- brug skruer med korrekt længde
- kontrollér at skruerne ikke går for langt op i motoren
- før motorledninger, så de ikke kan ramme propeller

Motorretning kan kontrolleres senere i software, men kun **uden propeller**.

## 6. Montering af elektronik

Montér herefter:

- 4-i-1 ESC
- flight controller
- eventuelle afstandsstykker eller vibrationsdæmpning hvis relevant

Kontrollér:

- at ESC og flight controller vender korrekt
- at USB-adgang stadig er praktisk
- at der er plads til kondensator og strømledning

## 7. Lodning og strømforbindelser

Lodning skal foretages roligt og kontrolleret:

- lod batteriledning og XT60-forbindelse korrekt
- montér kondensator efter producentens anbefaling
- lod motorledninger til ESC hvis nødvendigt
- forbind ESC og flight controller korrekt

Efter hver større lodning:

- kontrollér for loddebroer
- kontrollér polaritet
- brug gerne multimeter til kontinuitetskontrol

Tilslut aldrig batteri, hvis du er i tvivl om polaritet eller kortslutning.

## 8. Ledningsføring til GPS, receiver og buzzer

### GPS

- tilslut GPS til korrekt UART
- montér modulet, så det får bedst mulig fri udsigt opad
- undgå unødvendig elektrisk støj tæt på GPS-ledninger

### Receiver

- tilslut receiver efter korrekt protokol og pinout
- montér antenner, så de ikke klemmes eller rammer propeller

### Buzzer

- tilslut buzzer til flight controllerens relevante udgang
- montér den, så den kan høres og stadig er beskyttet

## 9. Softwareopsætning

Når hardwaren er samlet, kan softwaren sættes op:

1. Installér INAV Configurator
2. Verificér officiel understøttelse af valgt flight controller og target
3. Forbind med USB
4. Kontrollér board orientation
5. Konfigurér receiver
6. Konfigurér GPS
7. Konfigurér modes
8. Indstil batteriovervågning for 4S
9. Indstil failsafe
10. Aktivér og test Return to Home trinvist

> Alle disse trin skal udføres **uden propeller monteret**.

## 10. Pre-flight tests

Før første flyvning skal følgende testes:

- at dronen armer korrekt
- at receiverkanaler bevæger sig rigtigt
- at motorerne reagerer i korrekt retning
- at spændingsvisning virker rimeligt
- at GPS får data
- at failsafe opfører sig som forventet
- at buzzer kan aktiveres

Hvis noget opfører sig forkert, skal det løses på arbejdsbordet først.

## 11. Første flyvning

Den første flyvning skal ske:

- i et åbent område
- med god afstand til mennesker, bygninger og veje
- i roligt vejr
- med en enkel flyveplan

Start med korte løft og simple manøvrer:

- check stabilitet
- check radioforbindelse
- check batteriforbrug
- land tidligt og inspicér dronen bagefter

## 12. Test af Return to Home

Return to Home skal **ikke** være det første, der afprøves i luften. Først skal:

- GPS være stabil
- hjemmepunkt være korrekt registreret
- almindelig line-of-sight kontrol være bekræftet
- failsafe være forstået

RTH skal kun testes i et **kontrolleret, åbent område** med god sikkerhedsafstand. Testen skal være planlagt og overvåget, så piloten kan overtage kontrollen, hvis adfærden ikke er som forventet.

## 13. Efterkontrol og forbedringer

Efter de første testdage kan projektet forbedres ved at:

- notere observationer
- justere kabelføring og mekanisk fastgørelse
- kontrollere skruer og vibrationer
- opdatere dokumentationen

Gå kun videre til større ændringer, når den nuværende opsætning er forstået og virker stabilt.
