# Jakobs drone

> **Status: planlægning / under opbygning**
>
> Dette repository er første dokumentationsgrundlag for et skoleprojekt. Indholdet beskriver bekræftede projektvalg og områder, der stadig skal valideres, før konkrete komponenter købes.

## Formål

**Jakobs drone** er et dansk open source-skoleprojekt for en elev i **9. klasse**. Målet er at planlægge, bygge, konfigurere og teste en 5-tommer quadcopter på en måde, som er lærerig, realistisk og sikker for en begynder.

Projektet er dokumentationsdrevet: først skal krav, sikkerhed, indkøb og arbejdsgange være på plads, og derefter kan de endelige hardwarevalg bekræftes.

## Bekræftede designvalg

Følgende projektbeslutninger er fastlagt:

- **5-tommer frame**
- **INAV** som flight-controller software
- **GPS**
- **Return to Home (RTH)**
- **Ingen FPV i version 1**
- **4S LiPo i første version**
- **4-i-1 ESC med 3-6S understøttelse**, så en senere 6S-opgradering fortsat er mulig
- **Line-of-sight styring** i stedet for FPV i første version

## Hvem er projektet til?

Projektet er skrevet til en ung begynder og skal kunne forstås af en elev i 9. klasse med voksen støtte ved lodning, batterihåndtering og første testflyvninger.

Fokus er på:

- planlægning
- sikkerhed
- indkøb og kompatibilitet
- mekanisk samling
- lodning og ledningsføring
- konfiguration i INAV
- test uden propeller
- kontrolleret første flyvning

## INAV

Projektet bygger på officielle INAV-ressourcer:

- Officiel hjemmeside: <https://inavflight.com/>
- Kildekode: <https://github.com/iNavFlight/inav>
- INAV Configurator: <https://github.com/iNavFlight/inav-configurator>

## Dokumentation i repositoryet

- [Software og opsætning](docs/software.md)
- [Indkøbsliste](docs/indkoebsliste.md)
- [Instruktionsmanual](docs/instruktionsmanual.md)
- [Sikkerhed](docs/sikkerhed.md)
- [Projektplan](docs/projektplan.md)

## Hvad er afklaret, og hvad mangler stadig?

### Afklaret

- Dronen skal være en **5-tommer quadcopter**
- Første version skal være **uden FPV**
- Den skal bruge **INAV**, **GPS** og **Return to Home**
- Den skal flyve på **4S** fra start
- ESC'en skal vælges, så den også kan klare **3-6S**

### Skal stadig valideres

- Hvilken **flight controller** der har dokumenteret INAV-understøttelse i en relevant version
- Hvilket **firmware-target** INAV understøtter til den valgte controller
- Om valgt **GPS-modul**, **receiverprotokol**, **stack-størrelse** og **strømkrav** passer sammen
- Hvilke konkrete motorer, propeller og strømgrænser der passer til 4S nu og en mulig 6S-opgradering senere

Repositoryet skelner derfor mellem **foreløbigt anbefalede dele** og **endeligt bekræftede køb**. Der findes nu en konkret anbefalet version 1, men den skal stadig valideres mod aktuel INAV-understøttelse, fysisk montage og leveringsindhold, før der bestilles.

## Aktuel indkøbsstatus

Projektet er nu kommet længere end den helt tidlige idéfase. Der er udarbejdet en konkret indkøbsliste med teknisk begrundelse, prisoverslag, kompatibilitetskontrol og alternativer:

- [Indkøbsliste](docs/indkoebsliste.md)

Det betyder, at projektet ikke længere kun beskriver generelle produktkategorier. Der er nu en **foreløbig anbefalet version 1**, som kan bruges som arbejdshypotese for videre kontrol.

### Foreløbigt anbefalet version 1

Den nuværende anbefaling bygger på følgende hoveddele:

- **iFlight Nazgul XL5 ECO V1.1** frame
- **Flywoo GOKU F722 Pro V2 55A 30×30 Stack** som FC + ESC
- **4 × iFlight XING-E 2207 2450KV** motorer
- **TBS M10 GPS/GLONASS** eller tilsvarende M10 GPS-modul
- **RadioMaster RP1 ExpressLRS 2.4 GHz** receiver
- **RadioMaster Pocket ExpressLRS 2.4 GHz** sender
- **CNHL Black Series 1500 mAh 4S 130C** LiPo
- **Gemfan Hurricane 51433** propeller
- **VIFLY Finder 2** buzzer

Denne kombination er dokumenteret som en teknisk sammenhængende **4S-version 1**, hvor ESC'en samtidig bevarer mulighed for senere 6S-opgradering.

### Foreløbigt budget

Den kendte produktpris er cirka **€502,66**, svarende til cirka **3.750 DKK** før fragt og småmaterialer.

Et mere realistisk samlet budget for første version er cirka:

- **4.100 til 4.700 DKK** afhængigt af fragt, sikkerhedsudstyr og mindre el-dele

Beløbene skal stadig betragtes som **overslag**, fordi priser, lagerstatus, fragt og valutakurs kan ændre sig.

## Hvad er undersøgt om kompatibilitet?

På nuværende tidspunkt peger dokumentationen på, at følgende allerede ser fornuftigt ud:

- **Frame og stack** matcher mekanisk i **30,5 × 30,5 mm**
- **Frame og motorer** matcher i **16 × 16 mm** monteringsmønster
- **Motorer og propeller** matcher via **M5-aksel / M5-propelhul**
- **4S-batteri og XT60-strømvej** passer til den planlagte første version
- **ESC-marginen** ser nominelt god ud i forhold til motorernes oplyste strømforbrug
- **Receiver og GPS** kan i princippet fordeles på flight controllerens UARTs
- **ExpressLRS + CRSF** er en relevant line-of-sight-løsning til projektet

Derudover er der allerede identificeret vigtige 6S-begrænsninger:

- ESC'en kan bevares ved en senere opgradering
- motorerne på **2450KV** er valgt til **4S**, ikke som permanent 6S-valg
- ved normal 6S-opgradering bør motorerne som udgangspunkt skiftes til lavere KV

## Hvad skal stadig dobbelttjekkes før bestilling?

Selv om projektet er kommet længere, mangler der stadig nogle afgørende kontroller før endeligt køb:

- at den valgte **flight controller** stadig har dokumenteret **INAV-understøttelse**
- at det korrekte **firmware-target** stadig findes i den aktuelle INAV Configurator
- at producentens **pinout** passer til den planlagte tilslutning af receiver, GPS, buzzer og eventuel ESC-telemetri
- at den konkrete stack faktisk leveres med eller uden **XT60-ledning**, **kondensator** og øvrige smådele
- at valgt **batteri** fysisk passer i frame og kan fastgøres sikkert
- at der findes en egnet **GPS-holder** eller praktisk monteringsløsning
- at **LiPo-fragt til Danmark** og samlet lagerstatus er realistisk ved checkout
- at sender og receiver bruger kompatibel **ExpressLRS-firmware** og korrekt binding phrase

## Indkøbsstrategi lige nu

Den mest realistiske strategi i projektets nuværende fase er:

1. Brug den eksisterende BOM som **arbejdsgrundlag**
2. Bekræft **INAV-target** og pinout før bestilling
3. Bekræft hvilke smådele der mangler i pakken
4. Bekræft lagerstatus og fragt for batterier
5. Gennemfør først derefter den endelige bestilling

Målet er altså ikke bare at købe “noget der ligner”, men at købe en **dokumenteret kompatibel første version**.

## Indkøbspolitik for version 1

Når der senere vælges konkrete dele, skal projektet så vidt muligt bruge **europæiske salgssteder** for indkøb. Det gør levering, support, returhåndtering og overblik lettere i et skoleprojekt.

De nuværende hovedkandidater blandt europæiske salgssteder er **FPV24** og **iFlight Europe**, men lagerstatus, fragt og samlet ordresammensætning skal stadig kontrolleres ved den endelige bestilling.

Det er muligt at undersøge **iFlight** som en potentiel producent eller produktlinje til enkelte dele, men det er **ikke et bekræftet slutvalg**. Hvis iFlight-komponenter overvejes, skal de stadig:

- købes via et egnet europæisk salgssted, hvis muligt
- passe til projektets 4S-krav og fremtidige 3-6S-ESC-strategi
- have dokumenteret kompatibilitet med den valgte INAV-opsætning
