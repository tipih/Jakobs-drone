# Software

## Hvad er INAV?

**INAV** er open source software til flight controllere. Det bruges til at styre en drone, så den kan holde stabil flyvning og bruge funktioner som GPS, failsafe og **Return to Home**.

Til dette projekt er INAV valgt, fordi det passer godt til en drone, der skal flyves med **line-of-sight**, bruge **GPS**, og kunne vende tilbage mod hjemmepunktet, hvis opsætningen er korrekt testet.

## Officielle links

- INAV hjemmeside: <https://inavflight.com/>
- INAV kildekode: <https://github.com/iNavFlight/inav>
- INAV Configurator: <https://github.com/iNavFlight/inav-configurator>

## Vigtig afgrænsning før indkøb

Den **præcise INAV-version** og det **understøttede flight-controller target** skal verificeres, **før der købes hardware**. En flight controller er ikke automatisk egnet, bare fordi den ligner andre modeller eller tidligere har været nævnt i et forum.

Før køb skal der derfor kontrolleres:

- at den ønskede flight controller faktisk understøttes af en aktuel INAV-version
- at det rigtige firmware-target stadig findes i de officielle INAV-ressourcer
- at controlleren har de nødvendige porte til GPS, receiver, ESC-signaler, buzzer og eventuel batterimåling

## Planlagt konfigurationsworkflow

Følgende arbejdsgang er den planlagte opsætning for projektet:

1. **Installer firmware og configurator**
   - Installer INAV Configurator på computeren.
   - Kontrollér hvilken INAV-version der er relevant for den valgte flight controller.
   - Flash kun firmware, der matcher den dokumenterede target-understøttelse.

2. **Kontrollér board orientation**
   - Bekræft at flight controllerens fysiske monteringsretning svarer til opsætningen i INAV.
   - Hvis controlleren er monteret roteret, skal det indstilles korrekt i softwaren.

3. **Sæt receiver op**
   - Vælg korrekt receiverprotokol for den radio, der bruges til line-of-sight flyvning.
   - Kontrollér at kanaler bevæger sig rigtigt i configurator, og at midtpunkter og endepunkter er rimelige.

4. **Sæt GPS op**
   - Tilslut GPS til korrekt UART.
   - Kontrollér at GPS-data modtages stabilt.
   - Bekræft placering og orientering, så signal og retningsdata ikke forstyrres unødigt.

5. **Indstil modes**
   - Tildel arming, flyvetilstande og eventuelle hjælpefunktioner til kontakter på senderen.
   - Indstil kun modes, der er forstået og testet trinvist.

6. **Konfigurer batteriovervågning**
   - Indstil korrekt batteritype og spændingsovervågning til 4S-drift.
   - Bekræft at spændingsmålingen er realistisk, før dronen flyves.

7. **Konfigurer failsafe**
   - Indstil failsafe, så dronen reagerer forudsigeligt ved tab af radiosignal.
   - Brug ikke standardantagelser; kontrollér altid den faktiske adfærd.

8. **Konfigurer Return to Home**
   - Aktivér RTH først når GPS, hjemmepunkt og failsafe er korrekt sat op.
   - Husk at RTH skal betragtes som en hjælpefunktion, ikke som en garanti.

9. **Udfør bench tests uden propeller**
   - Alle softwaretests og motorchecks skal udføres **uden propeller monteret**.
   - Kontrollér sensorretning, GPS-data, receiverinput, arming-logik og failsafe-adfærd på arbejdsbordet først.

## Hvad vi endnu ikke fastlåser

Dette dokument beskriver workflow og kontrolpunkter, men **fastlåser ikke endnu**:

- konkret flight-controller model
- konkret INAV-version
- konkret firmware-target

De valg må først bekræftes, når kompatibiliteten er dokumenteret i officielle INAV-kilder.
