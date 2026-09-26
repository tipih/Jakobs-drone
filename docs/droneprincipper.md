# Sådan virker en drone

Dette dokument forklarer, hvordan en drone med fire propeller virker, og hvad de forskellige dele i Jakobs drone bruges til.

Dokumentet handler om teorien bag dronen. Det forklarer ikke, hvordan delene skal samles. Det kan du i stedet læse om i [instruktionsmanualen](instruktionsmanual.md).

## Indholdsfortegnelse

- [Hvad er en quadcopter?](#hvad-er-en-quadcopter)
- [Hvordan kan dronen flyve?](#hvordan-kan-dronen-flyve)
- [Fra batteri til løft](#fra-batteri-til-løft)
- [Sådan styrer man dronen](#sådan-styrer-man-dronen)
- [Flight controlleren holder dronen stabil](#flight-controlleren-holder-dronen-stabil)
- [GPS og Return to Home](#gps-og-return-to-home)
- [Dronens vigtigste dele](#dronens-vigtigste-dele)
- [Batteri, strøm og flyvetid](#batteri-strøm-og-flyvetid)
- [Vigtige sikkerhedsregler](#vigtige-sikkerhedsregler)
- [Forkortelser](#forkortelser)
- [Kort opsummering](#kort-opsummering)

## Hvad er en quadcopter?

En quadcopter er en drone med fire motorer og fire propeller. Navnet kommer af ordet quad, som betyder fire.

Når propellerne drejer rundt, skubber de luft nedad. Samtidig bliver dronen skubbet opad. Den opadgående kraft kaldes løft.

Det kan sammenlignes med at hoppe fra jorden. Når du skubber ned mod jorden med benene, bliver din krop skubbet opad. Propellerne gør noget lignende, men de skubber mod luften.

Dronens bevægelse afhænger af forholdet mellem løftet og dens vægt:

- Hvis løftet er større end dronens vægt, stiger dronen.
- Hvis løftet er mindre end dronens vægt, falder dronen.
- Hvis løftet passer til dronens vægt, kan den holde samme højde.

Sammenhængen kan skrives som:

T = m * g

Her betyder:

- `T`: den samlede løftekraft
- `m`: dronens masse i kilogram
- `g`: tyngdeaccelerationen, cirka 9,82 m/s²

Man behøver ikke kunne bruge formlen for at forstå princippet. Det vigtigste er, at propellerne skal skabe nok løft til at holde dronen i luften.

## Hvordan kan dronen flyve?

Dronen har fire motorer, som hver drejer en propel. Flight controlleren kan ændre hastigheden på hver motor.

Når motorerne kører hurtigere, drejer propellerne hurtigere og skaber mere løft. Når motorerne kører langsommere, skaber propellerne mindre løft.

Derfor kan dronen bevæge sig ved at ændre hastigheden på motorerne:

- Alle motorer hurtigere får dronen til at stige.
- Alle motorer langsommere får dronen til at falde.
- Motorerne i den ene side hurtigere får dronen til at hælde.
- Forskellig hastighed på bestemte motorer får dronen til at dreje.

Løftet vokser meget, når propellens hastighed stiger. En lille ændring i motorens hastighed kan derfor ændre dronens bevægelse tydeligt.

## Fra batteri til løft

Energien bevæger sig gennem dronen på denne måde:

```text
Batteri -> Flight controller og ESC -> Motorer -> Propeller -> Løft og bevægelse
```


Receiveren, GPS-modulet og sensorerne sender samtidig information til flight controlleren.

Processen foregår i fire trin:

1. **Batteriet leverer strøm:** LiPo-batteriet leverer elektrisk energi til motorerne og elektronikken.
2. **Flight controlleren beregner styringen:** Den modtager pilotens kommandoer og målinger fra dronens sensorer.
3. **ESC'en styrer motorerne:** Den modtager besked fra flight controlleren om, hvor hurtigt hver motor skal køre.
4. **Propellerne skaber løft:** Motorerne drejer propellerne, som skubber luft nedad og dermed løfter dronen op.

## Sådan styrer man dronen

En drone kan bevæge sig på fire grundlæggende måder:

| Styring | Hvad gør dronen? | Hvordan sker det? |
|---|---|---|
| Throttle | Stiger eller falder | Alle fire motorer ændrer hastighed samtidig. |
| Roll | Hælder til højre eller venstre | Motorerne i den ene side skaber mere løft end motorerne i den anden side. |
| Pitch | Hælder frem eller tilbage | De forreste og bagerste motorer skaber forskelligt løft. |
| Yaw | Drejer til højre eller venstre | Motorernes hastighed ændres, så dronen drejer om sin egen lodrette akse. |

### Throttle

Throttle bestemmer, hvor meget kraft motorerne skal levere.

Når piloten giver mere throttle, kører alle motorerne hurtigere. Dronen får mere løft og stiger.

Når piloten giver mindre throttle, kører motorerne langsommere. Dronen får mindre løft og falder.

### Roll

Roll betyder, at dronen hælder til højre eller venstre.

Hvis motorerne i venstre side skaber mere løft end motorerne i højre side, hælder dronen mod højre.

Hvis motorerne i højre side skaber mere løft, hælder den mod venstre.

### Pitch

Pitch betyder, at dronen hælder frem eller tilbage.

Hvis de bagerste motorer skaber mere løft end de forreste, hælder dronen fremad.

Hvis de forreste motorer skaber mere løft, hælder dronen bagud.

### Yaw

Yaw betyder, at dronen drejer rundt om sin egen lodrette akse.

To af propellerne drejer med uret, mens de to andre drejer mod uret. Det er nødvendigt, fordi hver propel påvirker dronen med en drejekraft.

Hvis alle propeller drejede samme vej, ville hele dronen forsøge at dreje den modsatte vej. Ved at bruge to propeller i hver retning udligner kræfterne normalt hinanden.

Flight controlleren kan ændre denne balance, når dronen skal dreje.

### Hvordan flyver dronen fremad?

Når dronen hælder fremad, peger en del af løftekraften også fremad. Det får dronen til at bevæge sig frem.

Det samme gælder, når den hælder til siden. En del af løftet trækker så dronen mod højre eller venstre.

Når dronen hælder, bliver der samtidig lidt mindre løft direkte opad. Flight controlleren kan derfor være nødt til at øge motorernes hastighed for at holde samme højde.

## Flight controlleren holder dronen stabil

Flight controlleren er dronens lille computer. Den styrer motorerne og forsøger hele tiden at holde dronen stabil.

Flight controlleren modtager information fra:

- pilotens fjernbetjening
- dronens gyro
- dronens accelerometer
- GPS-modulet
- andre tilsluttede sensorer

### Gyro og accelerometer

Gyroen måler, hvor hurtigt dronen drejer eller ændrer retning.

Accelerometeret måler acceleration og kan blandt andet hjælpe med at registrere, hvordan dronen hælder.

Gyroen og accelerometeret er ofte samlet i en enhed, som kaldes en IMU.

Flight controlleren sammenligner pilotens ønske med sensorernes målinger.

Hvis piloten for eksempel ønsker, at dronen skal flyve lige frem, men vinden skubber den til siden, forsøger flight controlleren at rette op på bevægelsen ved at ændre motorernes hastighed.

Det sker mange gange i sekundet.

### PID-regulering

Flight controlleren bruger ofte noget, der hedder en PID-regulator. Den hjælper med at beregne, hvordan motorerne skal ændre hastighed for at holde dronen stabil.

PID består af tre dele:

- **P** reagerer på den fejl, der findes lige nu.
- **I** reagerer på en fejl, der har været der i længere tid.
- **D** reagerer på, hvor hurtigt fejlen ændrer sig.

Man kan sammenligne det med at holde balancen på en cykel:

Hvis cyklen hælder, styrer man til siden for at rette den op.
Hvis man retter for kraftigt, kan cyklen begynde at slingre.
Hvis man retter for lidt, kan man vælte.

På samme måde skal dronens regulering være hurtig, men samtidig rolig og præcis.

PID-indstillingerne bør ikke ændres tilfældigt. Forkerte indstillinger kan få dronen til at ryste, blive ustabil eller få motorerne til at blive for varme.

## GPS og Return to Home

GPS-modulet modtager signaler fra satellitter. Ved hjælp af signalerne kan dronen beregne sin placering.

GPS kan blandt andet bruges til:

- at gemme dronens startposition
- at vise dronens position
- at holde en bestemt position
- at hjælpe med navigation
- at få dronen til at flyve tilbage mod startstedet

### Home position

Når dronen får et godt GPS-signal, kan den gemme sin startposition. Denne position kaldes ofte home position.

Det er vigtigt, at home position er korrekt registreret, før dronen letter. Ellers ved dronen ikke sikkert, hvor den skal flyve hen ved Return to Home.

### Return to Home

Return to Home, forkortet RTH, betyder, at dronen forsøger at flyve tilbage mod sin gemte home position.

en passende RTH-højde
RTH kræver blandt andet:

- et stabilt GPS-signal
- en korrekt gemt home position
- korrekt information om dronens retning
- en passende RTH-højde
- korrekt opsat failsafe
- fungerende batteriovervågning

RTH-højden skal være høj nok til, at dronen ikke rammer træer, bygninger eller andre forhindringer på vejen tilbage.

RTH er en hjælpefunktion. Den betyder ikke, at dronen altid automatisk kan komme sikkert hjem. GPS-fejl, forkert opsætning, lavt batteri eller forhindringer kan stadig skabe problemer.

Piloten skal derfor altid være klar til at overtage styringen.

### Failsafe

Failsafe er dronens sikkerhedsreaktion, hvis den for eksempel mister forbindelsen til fjernbetjeningen.

Afhængigt af opsætningen kan dronen blandt andet forsøge at:

- flyve tilbage til home position
- lande
- stoppe motorerne

En forkert opsat failsafe kan være farlig. Funktionen skal derfor indstilles og testes forsigtigt.

## Dronens vigtigste dele

| Del | Funktion |
|---|---|
| Frame | Dronens ramme. Den holder motorer, elektronik og batteri på plads. |
| LiPo-batteri | Leverer elektrisk energi til dronen. Projektet bruger et 4S-batteri. |
| XT60-stik og strømledning | Forbinder batteriet med dronens elektronik. Forbindelserne skal kunne tåle høj strøm. |
| Flight controller (FC) | Dronens computer. Den læser pilotens kommandoer og sensorerne og beregner, hvordan motorerne skal styres. |
| ESC | Styrer strømmen til motorerne og bestemmer, hvor hurtigt de skal køre. |
| FC + ESC-stack | Flight controller og ESC monteret sammen som en samlet elektronikenhed. |
| Motorer | Omdanner elektrisk energi til rotation. |
| Propeller | Skubber luft nedad og skaber løft. De skal monteres i den rigtige retning. |
| Receiver | Modtager radiosignaler fra pilotens fjernbetjening. |
| Sender | Pilotens fjernbetjening. Den sender kommandoer til dronen. |
| GPS | Beregner dronens position ved hjælp af satellitsignaler. |
| Buzzer | Afgiver lyd ved fejl og kan hjælpe med at finde dronen efter en landing eller et styrt. |
| Kondensator | Beskytter elektronikken mod korte spændingsspidser og hjælper med at reducere elektrisk støj. |
| INAV | Softwaren i flight controlleren. Den håndterer blandt andet styring, sensorer, GPS og sikkerhedsfunktioner. |

### Motorernes KV-tal

De valgte motorer er mærket 2207 2450KV.

2207 beskriver omtrent motorens størrelse:

- 22 mm er statorens diameter.
- 7 mm er statorens højde.

KV fortæller omtrent, hvor mange omdrejninger motoren forsøger at køre pr. minut for hver volt, når den ikke er belastet af en propel.

Et højt KV-tal betyder normalt, at motoren er beregnet til at dreje hurtigt. KV er ikke det samme som motorens effekt.

De valgte motorer passer til et 4S-setup med 5-tommer propeller.

## Batteri, strøm og flyvetid

Dronen bruger et LiPo-batteri. LiPo-batterier kan levere meget strøm og bruges derfor ofte i droner.

De skal behandles forsigtigt, fordi forkert opladning, kortslutning eller fysisk skade kan få batteriet til at blive meget varmt eller bryde i brand.

### Hvad betyder 4S?

Et 4S-batteri består af fire battericeller, som er forbundet i serie.

Hver celle har en nominel spænding på cirka 3,7 V.

Batteriets nominelle spænding er derfor:

4 * 3,7 V = 14,8 V

Når batteriet er fuldt opladet, er hver celle normalt 4,2 V.

Den samlede spænding er derfor:

4 * 4,2 V = 16,8 V

Et 4S-batteri kaldes altså ofte et 14,8 V-batteri, selv om spændingen er 16,8 V, når det er helt opladet.

### Spænding, strøm og effekt

Tre vigtige størrelser er:

- Spænding, som måles i volt.
- Strøm, som måles i ampere.
- Effekt, som måles i watt.

Effekten kan beregnes med formlen:

P = V * I

Her betyder:

- `P`: effekt i watt
- `V`: spænding i volt
- `I`: strøm i ampere

Hvis motorerne arbejder hårdt, bruger de mere strøm. Det giver:

- kortere flyvetid
- mere varme i motorer og ledninger
- større belastning af batteriet

### Batteriets kapacitet

Et batteri på 1500 mAh har en kapacitet på 1,5 Ah.

Batteriets energi kan omtrent beregnes sådan:

E = 14,8 V * 1,5 Ah

Det giver:

E = 22,2 Wh

Wh betyder watt-timer og beskriver, hvor meget energi batteriet omtrent kan indeholde.

Det fortæller dog ikke præcist, hvor længe dronen kan flyve.

Flyvetiden afhænger blandt andet af:

- dronens vægt
- motorernes strømforbrug
- propellernes størrelse og type
- vindforhold
- flyvestil
- batteriets alder og tilstand

Rolig flyvning bruger normalt mindre energi end hurtige accelerationer og høje hastigheder.

## Vigtige sikkerhedsregler

En drone med kraftige motorer og propeller er ikke legetøj. Propellerne kan forårsage alvorlige skader.

Derfor skal følgende regler altid følges:

1. **Fjern propellerne under opsætning:** Dronen må ikke have propeller monteret, når den forbindes til en computer eller konfigureres på arbejdsbordet.
2. **Kontrollér motorernes retning:** Motorer og propeller skal dreje i de retninger, som softwaren forventer.
3. **Kontrollér propellerne:** Propellerne skal vende rigtigt og være spændt ordentligt fast.
4. **Brug korrekt LiPo-oplader:** Et LiPo-batteri må kun oplades med en oplader, der er beregnet til LiPo-batterier.
5. **Hold øje med batteriet under opladning:** Et LiPo-batteri bør ikke oplades uden opsyn.
6. **Brug et åbent område til test:** De første flyvetest bør foregå langt fra mennesker, biler og bygninger.
7. **Kontrollér GPS før start:** Hvis RTH skal bruges, skal dronen have en gyldig GPS-position og en korrekt home position.
8. **Vær klar til at afbryde motorerne:** Piloten skal vide, hvilken kontakt der bruges til at aktivere og stoppe motorerne.
9. **Følg de gældende regler:** Dronen skal flyves efter de regler, der gælder i det område, hvor den bruges.

## Forkortelser

| Forkortelse | Betydning |
|---|---|
| A | Ampere. Enhed for elektrisk strøm. |
| Ah | Amperetimer. Bruges til at beskrive batterikapacitet. |
| BEC | En spændingsregulator, der leverer en passende spænding til dronens elektronik. |
| CRSF | En kommunikationsprotokol mellem receiveren og flight controlleren. |
| ELRS | ExpressLRS. Et radiosystem til kommunikation mellem sender og drone. |
| ESC | Electronic Speed Controller. Styrer strømmen til motorerne. |
| FC | Flight Controller. Dronens styrecomputer. |
| GPS | Satellitbaseret system til positionsbestemmelse. |
| IMU | En sensorenhed, som normalt indeholder gyro og accelerometer. |
| INAV | Software til flight controllere med blandt andet GPS-navigation og RTH. |
| KV | Et tal, der beskriver motorens omtrentlige omdrejningstal pr. volt uden belastning. |
| LiPo | Lithium Polymer. En batteritype, der kan levere meget strøm. |
| PID | En metode, som flight controlleren bruger til at stabilisere dronen. |
| RTH | Return to Home. Dronen forsøger at vende tilbage til sin gemte startposition. |
| S | Antallet af battericeller i serie. 4S betyder fire celler. |
| UART | En forbindelse, som flight controlleren bruger til at kommunikere med eksempelvis GPS og receiver. |
| V | Volt. Enhed for elektrisk spænding. |
| W | Watt. Enhed for elektrisk effekt. |
| Wh | Watt-timer. Enhed for elektrisk energi. |

## Kort opsummering

En quadcopter flyver ved hjælp af fire propeller, som skubber luft nedad og dermed skaber løft.

Flight controlleren er dronens computer. Den modtager kommandoer fra piloten og målinger fra sensorerne. Derefter ændrer den hele tiden hastigheden på de fire motorer for at styre og stabilisere dronen.

GPS kan hjælpe dronen med at kende sin position og vende tilbage mod startstedet. Funktioner som Return to Home kræver dog korrekt opsætning og erstatter ikke en ansvarlig pilot.

Batteriet leverer den energi, som motorerne og elektronikken bruger. Jo hårdere motorerne arbejder, desto mere strøm bruger dronen, og desto kortere bliver flyvetiden.

## Hvad er forbedret?

- **Sprog:** Kortere sætninger og forklaring af fagord første gang, de bruges.
- **Struktur:** Bevægelse, elektronik, navigation og batteri er forklaret i en mere logisk rækkefølge.
- **Niveau:** Den avancerede PID-formel og formlen for drejemoment er erstattet af praktiske forklaringer.
- **Forståelse:** Der er tilføjet eksempler, blandt andet cykelbalancen og forklaringen af fremadrettet flyvning.
- **Sikkerhed:** De vigtigste regler for propeller, LiPo-batteri, GPS og første flyvning er samlet i ét afsnit.