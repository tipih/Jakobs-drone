# INAV - Flight Controller Software

Dette dokument forklarer, hvad INAV er, hvad det kan, og hvordan man konfigurerer det til Jakobs drone.

INAV er softwaren, der kører på flight controlleren. Den styrer motorerne, læser sensorerne og håndterer navigationen. Uden INAV kan dronen ikke flyve.

## Indholdsfortegnelse

- [Hvad er INAV?](#hvad-er-inav)
- [Hvad kan INAV?](#hvad-kan-inav)
- [INAV Configurator - konfigurationsappen](#inav-configurator---konfigurationsappen)
- [Før du starter](#før-du-starter)
- [Trin 1: Installation og tilslutning](#trin-1-installation-og-tilslutning)
- [Trin 2: Firmwareflash](#trin-2-firmwareflash)
- [Trin 3: Grundlæggende opsætning](#trin-3-grundlæggende-opsætning)
- [Trin 4: Kalibrering af sensorer](#trin-4-kalibrering-af-sensorer)
- [Trin 5: Receiver og styring](#trin-5-receiver-og-styring)
- [Trin 6: Motor- og ESC-opsætning](#trin-6-motor--og-esc-opsætning)
- [Trin 7: GPS-opsætning](#trin-7-gps-opsætning)
- [Trin 8: PID-tuning](#trin-8-pid-tuning)
- [Trin 9: Failsafe og sikkerhed](#trin-9-failsafe-og-sikkerhed)
- [Vigtige sikkerhedsregler](#vigtige-sikkerhedsregler)
- [Forkortelser](#forkortelser)

## Hvad er INAV?

INAV er open source-software, der kører på flight controlleren. Navnet er en forkortelse for "Navigation with iNav".

Flight controlleren er en lille computer, som styrer dronen. INAV fortæller denne computer, hvad den skal gøre.

INAV læser hele tiden målinger fra:

- Fjernbetjeningen (pilotens kommandoer)
- Gyroen (rotationsmålinger)
- Accelerometeret (bevægelsesmålinger)
- GPS-modulet (positionsmålinger)
- Kompasset (retningsmålinger)
- Andre sensorer

Derefter beregner INAV, hvordan motorerne skal arbejde for at:

- Udføre pilotens kommandoer
- Holde dronen stabil
- Navigere efter GPS
- Holde dronen sikker

Alt dette sker mange hundrede gange i sekundet.

## Hvad kan INAV?

INAV kan meget mere end blot at stabilisere dronen. Her er de vigtigste funktioner:

| Funktion | Beskrivelse |
|---|---|
| **Flyvning og styring** | Læser pilotens kommandoer og styrer motorerne. Holder dronen stabil med PID-regulering. |
| **Altitude Hold** | Dronen holder automatisk samme højde uden pilotens indgriben. |
| **Position Hold** | Med GPS kan dronen holde en fast position. |
| **Return to Home (RTH)** | Dronen flyver automatisk tilbage til startstedet. |
| **Failsafe** | Hvis forbindelsen går tabt, udfører dronen en sikkerhedsreaktion (lande, RTH osv.). |
| **GPS-navigation** | Dronen kan følge waypoints eller kommandoer baseret på GPS. |
| **Telemetri** | Dronen sender information om batteri, position, højde og fejl til piloten. |
| **Sensor-fusionering** | Kombinerer data fra flere sensorer for at få præcis information om dronens tilstand. |
| **Logging** | Gemmer data fra flyvet til senere analyse. |

## INAV Configurator - konfigurationsappen

INAV Configurator er det program, du bruger til at konfigurere flight controlleren.

Det er en gratis app, som virker på Windows, Mac og Linux. Appen forbinder til flight controlleren via USB og lader dig:

- Flashe ny firmware
- Indstille sensorer
- Konfigurere receiver og fjernbetjening
- Indstille motorer og ESC
- Kalibrere GPS
- Ændre PID-værdier
- Teste servos og motorer
- Læse fejl og advarsler

**Hent INAV Configurator herfra:** https://github.com/iNavFlight/inav-configurator/releases

Download den nyeste version til dit operativsystem.

## Før du starter

### Vigtig sikkerhed

1. **Fjern propellerne fra dronen.** Dronen må ALDRIG have propeller på, når du forbinder den til computeren eller konfigurerer den.
2. **Fjern batteriet fra dronen.** Få helt styr på konfigurationen før batteriet er tilsluttet.
3. **Forbind dronen USB-kablet EFTER du har åbnet INAV Configurator.**

### Hvad skal du have klar?

- En computer med Windows, Mac eller Linux
- Et USB-kabel, som passer til din flight controller
- INAV Configurator installeret
- Den rigtige firmware til din flight controller
- Information om din receiver og fjernbetjening

## Trin 1: Installation og tilslutning

### Installér INAV Configurator

1. Gå til https://github.com/iNavFlight/inav-configurator/releases
2. Download den nyeste version til dit operativsystem
3. Installér programmet
4. Åbn INAV Configurator

### Tilslut flight controlleren

1. Åbn INAV Configurator **før** du forbinder dronen
2. Sørg for, at **propellerne er fjernet** fra dronen
3. Forbind flight controlleren til computeren med USB-kablet
4. Vent 2-3 sekunder på forbindelse
5. Hvis forbindelsen ikke etableres, se "Fejlfinding" nederst

### Vælg serielport og baudrate

I øverste højre hjørne af INAV Configurator:

1. Klik på dropdown under "Serial port"
2. Vælg den port, som flight controlleren er forbundet til (typisk `/dev/ttyUSB0` på Linux eller `COM3` på Windows)
3. Sørg for, at baudrate er sat til `115200`
4. Klik "Connect"

Hvis det virker, skifter knappen til grøn "Disconnect", og du kan se dronens status i programmet.

## Trin 2: Firmwareflash

Firmware er den software, som flight controlleren kører. Du skal flashe (installere) INAV-firmware til din flight controller.

### Find den rigtige firmware

1. I INAV Configurator, klik på "Firmware Flasher" (på venstre side)
2. Vælg "INAV" fra dropdown
3. Vælg den nyeste stabil version
4. Vælg din flight controller fra listen
5. Vælg "Load Online (Release)"

### Flash firmware

1. **Fjern batteriet fra dronen**
2. **Sørg for, at propellerne er fjernet**
3. Klik "Load Firmware Online"
4. Vær tålmodig - det kan tage et par minutter
5. Du ser besked om "Programming Complete"

Firmware er nu installeret.

## Trin 3: Grundlæggende opsætning

Efter firmware er flashet, går du til "Setup" fanen.

### Vælg dronetype

1. Klik "Setup" i venstre meny
2. Under "Aircraft Configuration", vælg dit dronetype:
   - For Jakobs drone: vælg **Quadcopter X**
3. Klik "Apply and Save"

### Indstil GPS-protokol

1. Gå til "Ports" under menuen
2. Find den UART-port, som GPS er tilsluttet til
3. Vælg "GPS" fra funktionslisten
4. Sørg for, at baudrate er `9600` (eller hvad GPS-modulet bruger)
5. Klik "Save and Reboot"

### Indstil receiver

1. Gå til "Receiver" fanen
2. Vælg din receiver-type:
   - For ExpressLRS (ELRS): vælg **CRSF** eller **Serial-based Receiver**
   - Sørg for, at UART-port og baudrate passer
3. Klik "Save and Reboot"

## Trin 4: Kalibrering af sensorer

Flight controlleren skal ved, hvordan sensoren placeres i forhold til luften.

### Kalibrér accelerometeret

1. Gå til "Setup" fanen
2. Placer dronen på en flad, plan overflade
3. Klik "Calibrate Accelerometer"
4. Vent på, at kalibreringen er færdig
5. Dronen må ikke rykkes under kalibreringen

### Kalibrér magnetometeret (kompas)

1. Gå til "Setup" fanen
2. Klik "Calibrate Magnetometer"
3. Hold dronen og drej den langsomt rundt alle tre akser
4. Fortsæt i 30-60 sekunder, til processen er færdig
5. Magnetometeret bruges til at bestemme dronens retning

### Test sensorerne

1. Gå til "Setup" fanen
2. Tjek "Gyro", "Accelerometer" og "Magnetometer" statusser
3. Alle skal vise **OK** eller **READY**
4. Hvis nogen viser fejl, er der et problem med sensoren

## Trin 5: Receiver og styring

INAV skal vide, hvordan den skal læse pilotens kommandoer fra fjernbetjeningen.

### Konfigurér receiver-input

1. Gå til "Receiver" fanen
2. Vælg din receiver-type (f.eks. CRSF for ExpressLRS)
3. Vælg den rigtige seriel-port
4. Sørg for, at baudrate passer til din receiver
5. Klik "Save and Reboot"

### Map kontrolkanaler

1. Gå til "Receiver" fanen
2. Du ser alle 16 kanaler
3. Sørg for, at følgende kanaler er sat korrekt:
   - **Channel 1 (Roll):** Styrkeaxis (side-til-side)
   - **Channel 2 (Pitch):** Styrkeaxis (frem-til-tilbage)
   - **Channel 3 (Throttle):** Gasreglage
   - **Channel 4 (Yaw):** Retning (rotationn)
   - **Channel 5:** Flight mode switch
   - **Channel 6:** andre funktioner (eksempelvis RTH)

### Test fjernbetjeningen

1. Gå til "Receiver" fanen
2. Se på kanalkurverne i øverste højre
3. Flyt styrespakerne på fjernbetjeningen
4. Kurverne skal bevæge sig, når du bevæger styrespakerne
5. Hvis ikke, er der forbindelsesfejl

## Trin 6: Motor- og ESC-opsætning

INAV skal vide, hvordan den skal tale med ESC'erne for at styre motorerne.

### Indstil ESC-protokol

1. Gå til "Configuration" fanen
2. Find afsnittet "ESC/Motor Features"
3. Vælg dit ESC-protocol:
   - For Jakobs drone: typisk **DSHOT600** (hvis ESC'erne understøtter det)
   - Alternativt: **PWM** eller **OneShot42**
4. Klik "Save and Reboot"

### Indstil motordirection

1. Gå til "Motors" fanen
2. Du ser fire motorer (M1, M2, M3, M4)
3. For hver motor, skal du bekræfte, at den drejer rigtigt

**Vigtig:** Propellerne skal være fjernet!

1. Sæt "Master Control" til omkring 10%
2. Klik på en motor-knap, f.eks. "Test Motor 1"
3. Motoren skal dreje rundt
4. Hvis den drejer forkert vej, skrub i "Reverse" boksen
5. Gentag for alle fire motorer

Motorenes rækkefølge for Jakobs drone:

| Motor | Placering | Drej-retning |
|---|---|---|
| M1 | Foroven til højre | Med uret |
| M2 | Forneden til venstre | Med uret |
| M3 | Forneden til højre | Mod uret |
| M4 | Foroven til venstre | Mod uret |

## Trin 7: GPS-opsætning

GPS lader dronen kende sin position og vende hjem automatisk.

### Indstil GPS-sensor

1. Gå til "Ports" fanen
2. Find UART-porten for GPS
3. Vælg **GPS** fra "Sensor input"
4. Sørg for, at baudrate er `9600`
5. Klik "Save and Reboot"

### Aktivér GPS-funktioner

1. Gå til "Configuration" fanen
2. Find afsnittet "GPS"
3. Sæt flueben på:
   - **Enable GPS**
   - **Enable Magnetic Compass**
4. Find afsnittet "Navigation"
5. Aktivér:
   - **Enable Air Mode** (valgfrit, for avancerede piloter)
   - **Enable RTH**

### Sæt RTH-højde

1. Find afsnittet "Return to Home" i Configuration
2. Indstil **RTH Altitude** til omkring 30-50 meter
3. Dette sikrer, at dronen flyver høj nok til at undgå forhindringer på vejen hjem

### Indstil failsafe

1. I "Configuration" finder du "Failsafe"
2. Indstil **Failsafe Procedure** til:
   - **RTH** (flyv hjem) eller
   - **LAND** (land på stedet)
3. Indstil **Failsafe Delay** til omkring 3 sekunder
4. Indstil **Failsafe Throttle** til omkring 1100 (motor-kommando ved failsafe)

## Trin 8: PID-tuning

PID-værdier bestemmer, hvor flot dronen flyver. For de fleste droner virker standard-værdierne fint.

**Ændre PID-værdier kan få dronen til at ryste, blive ustabil eller falde. Gør det kun, hvis dronen har problemer.**

### Se standard PID-værdier

1. Gå til "PID Tuning" fanen
2. Du ser tre kolonner: **P**, **I** og **D**
3. Du ser også tre rækker: **Roll**, **Pitch** og **Yaw**

### Sådan virker PID-værdier

- **P (Proportional):** Reagerer hurtigt på fejl. For høj værdi giver oscillering.
- **I (Integral):** Håndterer vedvarende fejl. For høj værdi giver langsomhed.
- **D (Derivative):** Dæmper bevægelse. For høj værdi forstyrres af støj.

### Hvis dronen ryster

1. Reducer **P**-værdi for den akse, der ryster
2. Test igen
3. Gør små ændringer: +/- 5-10

### Hvis dronen er ustabil

1. Øg **D**-værdi
2. Test igen

**Vigtigt:** Test kun på et åbent område langt fra mennesker og genstande!

## Trin 9: Failsafe og sikkerhed

Failsafe er dronens sikkerhedsreaktion, hvis der opstår problemer.

### Indstil failsafe-opsætning

1. Gå til "Configuration" fanen
2. Find "Failsafe Settings"
3. Indstil:
   - **Failsafe Procedure:** RTH eller LAND
   - **Failsafe Delay:** 2-3 sekunder (tid før failsafe udløses)
   - **Failsafe Throttle:** 1100 (motorkommando under failsafe)

### Test failsafe

**Vigtig:** Test kun på åbent område!

1. Tag dronen op og stil den i luften (eller hold den i hånden)
2. Gentag pilotkomiandoerne
3. Sluk fjernbetjeningen
4. Failsafe skal udløses efter 2-3 sekunder
5. Dronen skal enten lande eller vende hjem
6. Hvis ikke, er der konfigurationsfejl

### Batteri-failsafe

1. I "Configuration", find "Battery"
2. Sæt flueben på "Enable Battery Monitor"
3. Sørg for, at dronens spændingssensor er tilsluttet
4. Indstil **Low Battery Warning** til omkring 3,5V pr. celle
5. INAV vil advare dig, hvis batteriet løber tør

## Vigtige sikkerhedsregler

En drone kan være meget farlig, hvis den ikke er konfigureret rigtigt.

Følg altid disse regler:

1. **Fjern altid propellerne under konfiguration** på computeren. Propeller skal aldrig være på, når du flasher firmware eller ændrer opsætninger.

2. **Kontrollér motorretningen uden propeller.** Brug "Motors" fanen til at teste hver motor, og sørg for, at de drejer rigtigt. Hvis motorerne drejer forkert vej, flyver dronen ikke.

3. **Test failsafe på åbent område.** Hvis failsafe ikke virker, kan dronen blive til en ustyret projektil.

4. **Kalibrér sensorer ordentligt.** Hvis accelerometeret eller kompasset ikke er kalibreret rigtigt, vil dronen flyve ustabilt.

5. **Sørg for GPS-signal før RTH.** Return to Home kræver et stabilt GPS-signal og en korrekt gemt home position. Test det før første flyvning.

6. **Indstil batterimonitor.** Dronens batteri skal overvåges for at undgå, at det løber helt tomt i luften.

7. **Test på åbent område først.** De første test skal foregå langt fra mennesker, dyr, biler og bygninger.

8. **Vær ansvarlig pilot.** INAV kan hjælpe med at holde dronen stabil og sikker, men det erstatter ikke en kompetent pilot. Du skal altid være klar til at overtage styringen.

## Forkortelser

| Forkortelse | Betydning |
|---|---|
| AHRS | Attitude and Heading Reference System. Kombination af sensorer til at bestemme dronens retning og hældning. |
| BEC | Battery Elimination Circuit. Elektronik der leverer rigtig spænding til modtageren og andre komponenter. |
| CRSF | Crossfire Serial Protocol. En protokol for hurtig kommunikation mellem receiver og flight controller. |
| D | Derivative. Den afledte del af PID-regulering. Dæmper oscillering. |
| ELRS | ExpressLRS. Et radiosystem til fjernbetjening. |
| ESC | Electronic Speed Controller. Styrer strøm til motorerne. |
| FC | Flight Controller. Dronens computer. |
| GPS | Global Positioning System. Satellitbaseret positionering. |
| I | Integral. Den integrerede del af PID-regulering. Håndterer vedvarende fejl. |
| INAV | Open source software til flight controllers. Håndterer styring, GPS og navigation. |
| IMU | Inertial Measurement Unit. Sensorer (gyro + accelerometer). |
| P | Proportional. Den proportionale del af PID-regulering. Reagerer på fejl. |
| PID | Proportional-Integral-Derivative. En metode til at styre dronen stabilt. |
| RTH | Return to Home. Dronen flyver automatisk tilbage til startstedet. |
| UART | Universal Asynchronous Receiver-Transmitter. Seriel kommunikation mellem elektronik. |

---

**Næste trin:** når INAV er konfigureret, kan du læse [instruktionsmanualen](instruktionsmanual.md) for at samle dronen og teste den i praksis.
