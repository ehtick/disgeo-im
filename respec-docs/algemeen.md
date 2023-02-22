# Algemeen

<aside class="issue">
   <strong>LET OP</strong>: Biblio in <code>config.js</code> uitbreiden met:
   <code>[NEN3610-2021-ontw]</code>, <code>[gimeg]</code>, <code>[iso19107-2019]</code>, <i>modelleerprincipes</i>, <i>doc overzicht generieke onderwerpen</i>, <i>notitie ruimtelijke relaties?</i>, <i>handreiking geburik CRS</i>.
</aside>

## Geometrie

#### Aandachtspunten

<aside class="issue">
   <strong>LET OP</strong>: Referenties naar in <code>config.js</code> gedefinieerde bronnen mogelijk opnieuw maken.
</aside>

<aside class="issue">
   <strong>LET OP</strong>: Referenties naar bestanden in <code>../media/</code> in oorspronkelijke repo opnieuw maken. Kopieer benodigde media-bestanden naar eigen repo.
</aside>

<aside class="issue">
   <strong>LET OP</strong>: samenvoegen met paragraaf Modelleertechnische uitgangspunten.
</aside>

<aside class="issue">
   <strong>LET OP</strong>: Geometrie zien we nu als een <i>datatype</i> en niet als een <i>objecttype</i>

#### Bibliografie

| naam document | sectie | link | 
| --- | --- | --- |
| Overzicht generieke onderwerpen voor DisGeo informatiemodellering | 9. Geometrie | [url](https://geonovum.github.io/disgeo-imsor/documentatie/#geometrie) |
| Modelleerprincipes | 2. Definities (Geo)Informatieobject) | [url](https://geonovum.github.io/disgeo-imsor/modelleerprincipes/#definities) |
| Modelleerprincipes | 7. MIM-profiel voor DiSGeo | [url](https://geonovum.github.io/disgeo-imsor/modelleerprincipes/#mim-profiel-voor-dis-geo) |
| Notitie ruimtelijke en administratieve relaties NEN3610:2022 | - | [url](https://github.com/Geonovum/disgeo-im/blob/main/docs/thema/bestuurlijke-gebieden/benaming-relaties.md) |
|Handreiking gebruik coördinaatreferentiesystemen | - | [url](https://docs.geostandaarden.nl/crs/def-hr-crs-20220314/) |

### Uitgangspunten

Voor `...` van geometrieën gelden een aantal belangrijke principes die volgen uit verschillende standaarden en initiatieven. 

 - Coordinaatreferentiesystemen
 - Technologieën
 - NEN3610
 - GEometrie in het model
 - Uitganspunten EMSO

Geometrieën worden gebruikt voor de representatie van _locatie_, _oriëntatie_ en _vorm_ van objecten uit de werkelijkheid in een informatiemodel. De dimensie dimensie van de representatie kan variëren van 0D- tot 3D-objecten. Deze objecten worden altijd geplaatst in een 2-dimensionele, of 3-dimensionele ruimte.

#### Coordinaatreferentiesystemen (CRS)

Voor DiSGeo/Bestuurlijke Gebieden zijn vier typen coördinatiesystemen relevant:

- WGS 84 gebaseerd op ITRS, gebruikt voor GPS
- European Terrestrial Reference System 1989 (ETRS89)
- Rijksdriehoek systeem (RD)
- Linear Reference Systems (LRS) (zie ISO 19148:2021, RWS-BPS, NWB, EU INSPIRE)

<aside class="issue">
   <strong>NOTE</strong>: Url opnemen naar bronnen?
</aside>

<aside class="issue">
   <strong>VRAAG</strong>: Wordt dit een <i>algemeen</i> stuk (DiSGeo) of <i>specifiek bestuurlijke gebieden</i>?
   <br>
   <strong>Voorstel</strong>: Algemener neerzetten, voor onderdeel BG, dan verder aanscherpen.
</aside>

##### Ondersteunde CRS-en bij aanlevering

Het **toepassingsgebied** en de **dimensie** bepalen welke CRS-en bij aanlevering van geometrieën geldig zijn. Aan de ene kant bestaat er onderscheid in het toepassingsgebied. Er zijn objecten die vallen binnen het Europese deel van Nederland en objecten die vallen binnen de Nederlandse Exclusieve Economische Zone (EEZ) van de Noordzee. Aan de andere kant bestaat er onderscheid in de dimensie van geometrieën. Sommige geometrieën zijn 2-dimensionaal; anderen 3-dimensionaal. Voor objecten binnen het Europese deel van Nederland gelden de volgende CRS-en: _**RD**_ en _**ETRS89**_. Voor gebieden op zee is nog geen besluit genomen.

<aside class="issue">
  <strong>VRAAG</strong>: Hier wordt EEZ genoemd, maar er zijn vier typen op zee. willen we niet dichter bij benaming uit huidige model blijven <i>'~ op land'</i> en <i>'~ op zee'</i>? 
</aside>

Er zijn verschillende implementaties van ETRS89 in omloop. Wij nemen het [advies](https://geonovum.github.io/HR-CRS-Gebruik/#realisaties-van-etrs89-en-evrs) van het _Regional Reference Frame Sub-Commission for Europe_ (EUREF) over, om de ETRF2000-realisatie te gebruiken. Verder wordt bij aanlevering rekening gehouden met een lijnlengte van maximaal 200 meter. Dit besluit volgt het [langelijnenadvies](https://forum.pdok.nl/uploads/default/original/2X/c/c0795baa683bf3845c866ae4c576a880455be02a.pdf) van het NSGI. Dit [wordt geadviseerd](https://geonovum.github.io/HR-CRS-Gebruik/#vormvastheid) in [gebruik-crs](https://docs.geostandaarden.nl/crs/def-hr-crs-20220314/), in verband met compatibiliteit met **RDNAPTRANS™**.

Voor het CRS van **2D-geometrieen** gelden de volgende EPSG-codes:

| CRS-Naam | Code  | URI                                             |
|----------|-------|-------------------------------------------------|
| RD       | 28992 | http://www.opengis.net/def/crs/EPSG/9.9.1/28992 |
| ETRF2000 | 7931  | http://www.opengis.net/def/crs/EPSG/9.9.1/7931  |

Voor het CRS van **3D-geometrieen** gelden de volgende EPSG-codes:

| CRS-Naam | Code  | URI                                             |
|----------|-------|-------------------------------------------------|
| RDNAP    | 7415  | http://www.opengis.net/def/crs/EPSG/9.9.1/7415  |
| ETRF2000 | 9067  | http://www.opengis.net/def/crs/EPSG/9.9.1/9067  |

###### Bestuurlijk gebied

Binnen het thema bestuurlijk gebied bevatten een aantal objecten een geometrie die binnen het Europese deel van Nederland valt. In het informatiemodel zijn deze gebieden geclassificeerd als 'bestuurlijk gebied op land'. Het gaat om de volgende vijf objecten. 

 - Rijksgebied
 - Gemeentegebied
 - Provinciegebied
 - Waterschapsgebied
 - Veiligheidsregiogebied

<!-- 

#### Bestuurlijk gebied op zee

 - Territoriale Zee
 - Aansluitende Zone
 - Exclusieve Economische Zone
 - Continentaal Plat

Voor objecten binnen de EEZ geldt:
* ETRS89

<aside class="issue">
Het is nog niet volledig duidelijk welke CRS-en het beste gebruikt kunnen worden voor aanlevering van geometrieen in de EEZ.
</aside>

<aside class="issue">
Uitzoekpunt: de EEZ zone is mogelijk niet het enige disgeo object waarvoor geldt dat RD geen optie is. Wellicht ook de andere bestuurlijke gebieden op zee en wellicht windturbines op zee.
</aside> -->

##### Ondersteunde CRS-en bij uitlevering:

<aside class="issue">
   <strong>VRAAG</strong>: Aan- en uitleverprocessen al openemen?
   <br>
   <strong>Antwoord</strong>: Ja aan- en uitlevering al opnemen.
</aside>

Bij uitlevering als RD dezelfde realisaties beschikbaar als bij aanlevering.

Bij uitlevering als ETRS89 kan de geometrie, naast als dezelfde realisaties als bij aanlevering, ook als de geografische ensemble CRSen opgevraagd worden. Te weten:

>**NOTE**: In onderstaande tabellen extra kolom 'dimensie' (o.i.d.) opnemen? **Nee**: hanteer zelfde aanpak als tabellen 'aanlevering'.

| CRS-Naam | Code  | URI                                             |
|----------|-------|-------------------------------------------------|
| ETRS89   | 4258  | http://www.opengis.net/def/crs/EPSG/9.9.1/4258  |
| ETRS89   | 4937  | http://www.opengis.net/def/crs/EPSG/9.9.1/4937  |

Uitlevering via de WGS 84 CRSen is ook mogelijk via nultransformatie [zoals beschreven](https://docs.geostandaarden.nl/crs/crs/#wgs-84-gelijkstellen-aan-etrs89-nultransformatie) in [gebruik-crs](https://docs.geostandaarden.nl/crs/def-hr-crs-20220314/). Het gaat specifiek om:

| CRS-Naam | Code   | URI                                             |
|----------|--------|-------------------------------------------------|
| WGS 84   | 4326   | http://www.opengis.net/def/crs/EPSG/9.9.1/4326  |
| WGS 84   | 4979   | http://www.opengis.net/def/crs/EPSG/9.9.1/4979  |
| WGS 84   | CRS84  | http://www.opengis.net/def/crs/OGC/1.3/CRS84    |
| WGS 84h  | CRS84h | http://www.opengis.net/def/crs/OGC/0/CRS84h     |

Hierbij zijn CRS84 en CRS84h respectievelijk de long lat varianten van de WGS 84 realisaties 4326 en 4979.

<aside class="issue">
   <strong>LET OP</strong>: Schrijfwijze 'long lat varianten'
</aside>

In [](#crs-overview) is een schematische weergave van de ondersteunde CRS-en bij aanlevering en uitlevering opgenomen.

<figure id="crs-overview">
    <img src="https://github.com/Geonovum/disgeo-imsor/blob/master/documentatie/media/crs-overview.drawio.png" alt="Overview van CRS-en in DiSGeo"/>
    <figcaption>Overzicht van de ondersteunde CRS-en in het kader van DiSGeo bij aanlevering en uitlevering</figcaption>
</figure>

##### Nauwkeurigheid

Voor het aangeven van de nauwkeurigheid van de geometrieen in RD(NAP) en ETRS89 volgen we [het advies](https://docs.geostandaarden.nl/crs/crs/#nauwkeurigheid-van-coordinaten) van [gebruik-crs](https://docs.geostandaarden.nl/crs/def-hr-crs-20220314/).

#### NEN 3610
NEN 3610 [[NEN3610-2021-ontw]] zegt weinig specifieks over geometrie en geometrische vastlegging van objecten, anders dan dat ISO 19107:2020 normatief wordt aangehaald, waarin de ISO geometrietypen (o.a. `GM_Point`, `GM_Curve`, `GM_Surface`, `GM_Solid`) worden gedefinieerd. 

Inwinregels worden in sectormodellen bepaald. 

> "Inwinregels geven aan welke punten van een object ingemeten moeten worden en waar de geometrie van een geregistreerd object aan moet voldoen. Het leidt tot een vastgestelde geometrische weergave gericht op een specifieke toepassing." 

Paragraaf 8.4.4.3 Geometrie bevat een aantal uitgangspunten:
- Geometrie is een representatie van een object.
- Een objecttype kan nul of meer geometrische representaties hebben.
- De beschrijving van de 3D-werkelijkheid wordt ondersteund.
- Hoogte-informatie kan absoluut of relatief zijn; hierover staat in NEN 3610 een goede uitleg.

Paragraaf 9.12 gaat in op topologische relaties en geeft hier gestandaardiseerde namen voor.

Hoofdstuk 10 bevat regels en handreikingen over coördinaatreferentiesystemen die van belang kunnen zijn voor de SOR. 

#### Geometrie in model 

<aside class="issue">
   <strong>NOTE</strong>: Verwijzen naar document dat dit beschrijft. NIet volledige uitleg hier overnemen. In elk geval afbeelding niet opnemen.
</aside>

De handreiking Geometrie in model en GML [[gimeg]] legt inhoudelijk uit hoe het geometriemodel uit ISO 19107 [[iso-19107-2019]] kan worden toegepast en wat het geldende Nederlands profiel is (i.e. welke selectie is gemaakt uit de mogelijke geometrietypen). 

Een eis uit [[EMSO]] is: 
> aansluiting op Simple Features (ISO 19125)

Simple Features maakt een selectie uit het ISO 19107 geometriemodel. Het neemt daaruit alleen de meest gebruikelijke geometrietypen over. 

<aside class="issue">
   ISO 19125 definieert een model voor <strong>2 dimensionale </strong> geometrietypen. 3D geometrie is uitgesloten in deze standaard. In EMSO wordt echter wel een behoefte aan 3D geometrie geformuleerd.
</aside>

We hanteren dus Simple Features (ISO 19125) _+ een aantal aanvullingen voor zover nodig, waarschijnlijk in ieder geval voor bogen en volumes._

Simple Features gebruikt zoals gezegd geometrietypen uit de veel uitgebreidere standaard ISO 19107, waarin het volledige geometriemodel gedefinieerd is. De typen uit dit model hanteren we doorgaans als 'black box' typen of interfaces. Als achtergrondinformatie beschrijven we hier kort wat het geometriemodel van ISO 19107 inhoudt. 

<figure>
    <img src="https://github.com/Geonovum/disgeo-imsor/blob/master/documentatie/media/iso19107-geometry.png" alt="ISO 19107 Geometry"/>
    <figcaption>Het Geometry object met al zijn kenmerken zoals gedefinieerd in het ruimtelijk schema van ISO 19107.</figcaption>
</figure>

Het Geometry object, waarvan alle specifieke geometrietypen zoals punt, lijn, vlak en volume afgeleid zijn, heeft veel kenmerken en operaties. Belangrijk voor ons zijn: 
- `SRID`: dit modelleert de verwijzing naar het "Spatial Reference system", in ons geval het coördinaatreferentiesysteem. 
- `metadata`: optioneel attribuut voor het opnemen van verwijzingen naar documentatie die informatie geeft over de implementatie van het geometrie-object. Dit kunnen we wellicht gebruiken voor bijvoorbeeld de gerealiseerde nauwkeurigheid van de geometrie.

<aside class="note">
   *Spatial reference system* is een breder begrip dan *coördinaatreferentiesysteem*. Het gaat om een algemene locatieaanduiding, een "ruimtelijk referentiesysteem" dat niet alleen op basis van coördinaten kan werken maar ook op basis van bijvoorbeeld geografische naam of adres. 
</aside>

#### Uitgangspunten uit EMSO

<aside class="issue">
   <strong>VRAAG</strong>: <i>Kwaliteitsmetadata</i> (o.a. precisie) verder aanvullen met of verwijzen naar <i>Modelleerprincipes</i>).
</aside>

- De vastlegging van geometrie wordt zodanig vormgegeven dat de driedimensionale (3D) beschrijving van een object kan worden opgenomen.
- EMSO beschrijft een aantal algemene topologische regels over vlakdekkendheid en topologie, bv "Objecten op verschillende hoogten moeten goed op elkaar aansluiten waar ze elkaar raken en consistent zijn"
- Waar relevant wordt er kwaliteitsmetadata voor geometrieën opgenomen.
- De ruimtelijke dekking van de SOR is inclusief de territoriale zee.
- Het te gebruiken coördinatenstelsel is RD. 
- De [precisie](https://www.noraonline.nl/wiki/Geometrische_precisie) van coördinaten is op millimeterniveau en in RD betekent dit dat er coördinaten met 3 decimalen worden opgenomen.
- Gegeneraliseerde data objecttypen [worden niet opgenomen in de SOR](https://docs.geostandaarden.nl/disgeo/emso/#generalisatie). Ze kunnen wel onderdeel zijn van informatieproducten. Generalisatie is "het zinvol weglaten, vereenvoudigen, verplaatsen, vergroten, symboliseren en/of aggregeren van de geometrie van objecten (of op attribuutniveau)", ten behoeve van minder gedetailleerde kaartschalen.

<aside class ="issue">
   Is RD wel het juiste coördinaatreferentiesysteem?
   <br> - Het te gebruiken coördinaatreferentiesysteem, RD, is niet toereikend voor objecten die zich niet op land bevinden maar op territoriale zee, zoals windturbines. Echter, de gewenste ruimtelijke dekking van de SOR is inclusief de territoriale zee.
   <br>- Vanuit verschillende (basis)registraties is niet RD maar ETRS89 de eis. O.a. in de Omgevingswet (bron?). In het EMSO is van RD uitgegaan omdat veel bronhouders nog in RD werken. We moeten met experts bekijken of RD danwel ETRS op land de vereiste moet zijn. We kunnen hierbij ook gebruik maken van [hoofdstuk 3](https://docs.geostandaarden.nl/crs/cv-hr-crs-20211125/#aandachtspunten-bij-crs-in-informatiemodel-en-informatieketen) van de Handreiking CRS [gebruik-crs](https://docs.geostandaarden.nl/crs/def-hr-crs-20220314/).
   <br> - Op zee zijn noch RD noch ETRS89 geschikt; het is gebruikelijk om daar WGS-84 te hanteren.
</aside>

### Geometrie-aspecten per objecttype

<aside class="issue">
   <strong>ACTIE</strong>: Paragraaf 9.3 en 9.4 in elkaar schuiven.
</aside>

De volgende (meta)aspecten van geometrie moeten worden gedefinieerd per objecttype in het informatiemodel of de documentatie daarbij: 

#### Geometrietype
Het geometrietype wordt aangegeven door keuze van het juiste type uit het ISO 19107 Geometry Model (`GM_xxx`), passend binnen het profiel zoals gedefinieerd in [[gimeg]]. 

<figure>
    <img src="https://docs.geostandaarden.nl/nen3610/gimeg/media/86bee1823dfd4f2ae0112c0462d2ccec.png" alt="ISO 19107 ruimtelijk schema"/>
    <figcaption>Het ruimtelijk schema van ISO 19107, geometrische primitieven.</figcaption>
</figure>

<aside class="issue">
   Hierbij is het relevant om te definiëren en op schrijven welke varianten toegestaan zijn. Een `GM_Surface` of `GM_Curve` heeft nog allerlei mogelijke verschijningsvormen in het Geometry model. Voor de uitwisseling en het gebruik is het handig om dit in te perken.
</aside>

#### Dimensionaliteit

<aside class="issue">
   <strong>VRAAG</strong>: Dit onderdeel opnemen in dit document?
   <br>
   <strong>Antwoord</strong>: Ja, maar wel samenvoegen met andere onderdelen over <i>geometrie</i>.
</aside>

Het aantal dimensies kan impliciet worden aangegeven door geometrietype, aangevuld met een aanduiding dat het om 2.5D gaat in de definitie van het attribuut. 

`GM_Solid` is per definitie 3D, maar bij `GM_Surface`, `GM_Curve` en `GM_Point` (en composite/multi varianten hiervan) is het mogelijk om 2 of 3 posities per coördinaat op te nemen. De hoogte is dan de derde positie. Of de hoogte wel of niet wordt opgenomen in de coördinaten kunnen we aangeven in de definitie van het attribuut.

<!-- <aside class="example">
   Definitie van het attribuut `geometrie` van een geluidbron in het Informatiemodel Geluid.
   <figure>
       <img src="media/img-voorbeeld-3d.png" alt="Voorbeeld IMGeluid"/>
       <figcaption>Voorbeeld geometrietype omschrijving IMGeluid</figcaption>
   </figure>
</aside>

<aside class="issue">
   Is het wenselijk om een semantisch attribuut `hoogte` te modelleren zodat te zien is wat de hoogte van het object is zonder naar de coördinaten te kijken? Waar zou je dit modelleren, in de geometrie of in het objecttype/gegevensgroeptype? Moet dit überhaupt wel? in EMSO staat het niet dus het lijkt geen inhoudelijke eis te zijn.

   <strong>Aanvulling:</strong> Dit zou je kunnen overwegen indien de hele geometrie dezelfde hoogte heeft. En dat is bij een <code>GM_Point</code> ook weer beter voor te stellen dan bij <code>GM_Linestring</code> (bijv. één hoogteaanduiding voor een weg(deel) of <code>GM_Surface</code> (een plat dat van een gebouw), hoewel het wel zou kunnen. Maar het wordt complex indien het om een set met hoogtewaarden/-coördinaten gaat. Die moet je dan weer matchen met de geometrie. Bovendien vervalt dan het voordeel van 'direct inzicht'.
</aside> -->

<!-- #### 3D geometrie

<aside class="issue">Hoe we omgaan met 3D geometrie in de SOR moet nog verder worden uitgewerkt.

Een aantal vragen: 
- Is het mogelijk om van een object naast een 3D geometrie ook de 2D geometrie registreren? En is dat wenselijk? Op de korte termijn is er wellicht behoefte aan een flexibele aanbodkant waar organisaties als ze er aan toe zijn 3D kunnen aanleveren maar voorlopig wel 2D.
- Ook is er waarschijnlijk wel behoefte aan 2D geometrie bij afnemers. Is dit dan iets dat je in een product afleidt, of is het iets dat we in het informatiemodel ook modelleren?
- Kun je de 2D geometrie altijd afleiden uit de 3D geometrie?
</aside> -->

#### Nauwkeurigheidseisen

>**NOTE**: Dit onderwerp is al verder uitgewerkt in modelleerprincipes.

Wat onder nauwkeurigheid van geometrie wordt verstaan is goed gedefinieerd in standaarden. We gaan ervan uit dat wat in EMSO nauwkeurigheid wordt genoemd, hetzelfde is als [positionele juistheid](https://www.noraonline.nl/wiki/Positionele_juistheid) in het NORA raamwerk gegevenskwaliteit en hetzelfde als wat in de BGT positionele nauwkeurigheid wordt genoemd: 

> Onder positionele nauwkeurigheid verstaat men de mate waarin de opgeslagen coördinaten overeenkomen met de waarden in de werkelijkheid of de geaccepteerde afwijking.

Per objecttype geven we de toegestane kwaliteit voor de positionele nauwkeurigheid als een getal in centimeters (dat dan de toegestane afwijking weergeeft). MIM heeft hiervoor geen metadata-element. Een optie is om dit in een tabel vóór in de gegevenscatalogus op te nemen, zoals gedaan in de BGT catalogus op p. 23. 

<aside class="example">
<figure>
    <img src="https://github.com/Geonovum/disgeo-imsor/blob/master/documentatie/media/bgt-nauwkeurigheid.png" alt="Voorbeeld BGT"/>
    <figcaption>Tabel met nauwkeurigheidseisen in de BGT gegevenscatalogus</figcaption>
</figure>
</aside>

Eventueel zou het ook in het MIM aspect `Regels` bij de geometrie eigenschap van het desbetreffende objecttype gezet kunnen worden. 

<aside class="issue">
- Zoeken naar een manier om dit machineleesbaar vast te leggen.

<strong>VOORSTEL</strong>: 

Leg dit vast in een te definiëren metadata aspect bij de eigenschap in een MIM extensie voor geo. Het heeft mogelijk toegevoegde waarde om dit bij de data te kunnen terugvinden.

Vastleggen bij eigenschap heeft voorkeur boven vastleggen bij objecttype, omdat er mogelijk meerdere geometrie-eigenschappen komen bij een objecttype (Levels of Detail).
</aside>

#### Inwinregels

>**NOTE**: Dit onderwerp is al verder uitgewerkt in modelleerprincipes.

Verreweg de meeste objecttypen in de SOR hebben in hun huidige registratie al enige vorm van inwinregels. Eventueel zouden inwinregels in het MIM aspect `Regels` bij het geometrie attribuut van het desbetreffende objecttype gezet kunnen worden. 

Omdat dit vaak omvangrijke instructies zijn, zijn ze nu meestal in tekst uitgeschreven in een apart handboek of hoofdstuk van de gegevenscatalogus. We zoeken naar een manier om deze teksten wel te relateren aan de bijbehorende modelelementen (annotatie).

#### Topologische regels

>**NOTE**: Dit onderwerp is al verder uitgewerkt in modelleerprincipes? Kijk ook naar deze [notitie over ruimtelijke en administratieve relaties in NEN3610:2022](https://github.com/Geonovum/disgeo-im/blob/main/docs/thema/bestuurlijke-gebieden/benaming-relaties.md).

Voor ruimtelijke relaties tussen de objecten kunnen we gebruik maken van de topologische relaties zoals gedefinieerd in de Simple Features standaard [[iso-19125-1-2004]] en aangeraden in [[NEN3610-2021-ontw]] en [[sdw-bp]]. Deze relaties zijn geïmplementeerd in veel geografische softwareomgevingen en ook in GeoSPARQL: 

- **`Equals`** - gelijk
- **`Disjoint`** - disjunct (geen enkel punt gemeen)
- **`Touches`** - raakt
- **`Crosses`** - kruist
- **`Within`** - binnen
- **`Contains`** - bevat
- **`Intersects`** - doorsnijdt (geometrieën hebben op zijn minst één punt gemeen;
geometrieën kunnen verschillende dimensie hebben)

Deze relaties kun je gebruiken voor punt-, lijn- en vlakgeometrieën. Omdat er in de SOR meer met 3D wordt gewerkt, worden topologieregels complexer maar ook secundair aan de representatie van de werkelijke verhouding tussen objecten. Uit EMSO: 

> Het is belangrijker om ervoor te zorgen dat objecten die zich in de werkelijkheid op een bepaalde wijze tot elkaar verhouden (bijvoorbeeld een verharding ligt bovenop een overbrugging) ook in de registratie op deze wijze tot elkaar verhouden (bijvoorbeeld dat uit de z-coördinaten van de verharding en de overbrugging blijkt dat de verharding bovenop de overbrugging ligt). De exacte uitwerking van deze relaties in topologie-regels zal later in het traject verder worden opgepakt.

<aside class="issue">Welke objecttypen spelen een rol in de landsdekkendheid? Welke objecttypen hebben specifieke topologische relaties met elkaar? We hebben als modelleurs inhoudelijke expertise nodig om dit goed uit te werken.</aside>

#### Benodigde kwaliteitsmetadata

Wat voor kwaliteitsmetadata bij een objecttype wordt voorgeschreven, kan worden bepaald aan de hand van uitgangspunten in EMSO [§ 3.4.5](https://docs.geostandaarden.nl/disgeo/emso/#meta-gegevens-over-herkomst-en-kwaliteit). Dit kan zijn:
- plaatsbepalingspunten
- een brondocument / bronverwijzing anders dan plaatsbepalingspunten
- gerealiseerde nauwkeurigheid van de geometrie van het object in de vorm van een nauwkeurigheidsklasseaanduiding
- helemaal geen kwaliteitsmetadata

We gaan onze eerder uitgewerkte modelleerpatronen toetsen tegen dit onderwerp.

### Geometrie-object
Per individuele geometrie vastleggen:
- Coördinatenstelsel
- Geometrietype
- De coördinaten zelf
- Indien van toepassing, kwaliteitsmetadata zoals beschreven in [](#benodigde-kwaliteitsmetadata).

Het volstaat om een ISO 19107 geometrietype toe te passen in het informatiemodel (zie [](#geometrie-in-model) voor uitleg). Dit zorgt ervoor dat het coördinatenstelsel kan worden opgenomen, dat het geometrietype duidelijk is en dat de coördinaten zelf kunnen worden opgenomen.

<aside class="issue">
   Heeft het meerwaarde om in het informatiemodel op te nemen in welk CRS een geometrie ingewonnen moet worden? Dat zou een metadata aspect kunnen zijn net zoals nauwkeurigheidseis.
</aside>