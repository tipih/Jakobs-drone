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

Repositoryet undgår derfor bevidst at præsentere ubekræftede komponentmodeller som endelige valg.

## Indkøbspolitik for version 1

Når der senere vælges konkrete dele, skal projektet så vidt muligt bruge **europæiske salgssteder** for indkøb. Det gør levering, support, returhåndtering og overblik lettere i et skoleprojekt.

Et muligt eksempel på et europæisk salgssted, der kan undersøges senere, er **FPV24**, men også dette er i denne fase kun en reference til videre research og **ikke** et bekræftet indkøbsvalg.

Det er muligt at undersøge **iFlight** som en potentiel producent eller produktlinje til enkelte dele, men det er **ikke et bekræftet slutvalg**. Hvis iFlight-komponenter overvejes, skal de stadig:

- købes via et egnet europæisk salgssted, hvis muligt
- passe til projektets 4S-krav og fremtidige 3-6S-ESC-strategi
- have dokumenteret kompatibilitet med den valgte INAV-opsætning
