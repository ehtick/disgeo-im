# Inleiding

Dit document beschrijft het Conceptueel Informatiemodel Bestuurlijke gebieden (CIM-BG). Het model definieert bestuurlijke gebieden zoals gemeenten, provincies, waterschappen en maritieme zones, en hun relatie tot de verantwoordelijke overheidsorganisaties.

## Doel

Het CIM-BG beoogt geo-informatie over bestuurlijke gebieden in samenhang beschikbaar te maken. Dit betekent:
- Een eenduidige definitie van bestuurlijke gebieden en hun geometrie
- Een heldere relatie tussen gebieden en de openbare lichamen die erover besturen
- Een basis voor het beantwoorden van vragen als: "Waar ligt de grens?" en "Welk openbaar lichaam is verantwoordelijk voor dit gebied?"

## Achtergrond en scope

### Achtergrond

Het CIM-BG is ontwikkeld vanuit de visie dat geo-informatie in samenhang beschikbaar moet zijn. Deze visie is onderdeel van het programma [Zicht op Nederland](https://zichtopnl.nl/) (ZON), waarin overheidspartijen in de GI-beraad samenwerken aan betrouwbare en breed beschikbare ruimtelijke informatie. Het document "Eisen aan model samenhangende objectenregistratie" ([[EMSO]]) beschrijft de uitgangspunten voor het modelleren van geo-objecten in samenhang. Het CIM-BG past deze uitgangspunten toe.

### Bestuurlijke Gebieden

Het opstellen van een conceptueel informatiemodel voor bestuurlijke gebieden als onderwerp komt voort uit:
- De behoefte aan een samenhangende voorziening voor bestuurlijke gebieden
- Het gebruik in verschillende registraties en informatieproducten, zoals bijvoorbeeld in het Digitaal Stelsel Omgevingswet (DSO), waar bestuurlijke grenzen bepalen wie het bevoegd gezag is
- De wens om te kunnen beantwoorden: "Wie is het bevoegd gezag op deze locatie?" en "Waar ligt de grens tussen bestuurlijke gebieden?"

### Scope informatiemodel

Dit informatiemodel beschrijft bestuurlijke gebieden (met hun geometrie) en hun relatie met de openbare lichamen die erover bestuur uitoefenen. Voor gedetailleerde informatie over overheidsorganisaties wordt verwezen naar het Register van Overheidsorganisaties (ROO) en TOOI.

De volgende typen bestuurlijke gebieden zijn in scope:

- Landgebied
- Provinciegebied
- Gemeentegebied
- Waterschapsgebied
- Veiligheidsregiogebied
- Maritieme zones: territoriale zee, aansluitende zone, exclusieve economische zone en het continentaal plat

De achtergrond, rationale en volledige scope-afbakening worden beschreven in het [scopedocument Bestuurlijke Gebieden](https://geonovum.github.io/disgeo-scope/bestuurlijkegebieden/). Overige scopedocumenten worden ontwikkeld in de [GitHub repository voor scopedocumenten](https://github.com/Geonovum/disgeo-scope/).

#### Samenwerkingsorganisaties in scope

Naast veiligheidsregio's bestaan er diverse andere typen samenwerkingsorganisatie, zoals omgevingsdiensten, GGD's en recreatieschappen. In deze eerste versie van het informatiemodel zijn **veiligheidsregio's** het enige type samenwerkingsorganisatie in scope.

In toekomstige versies kunnen andere typen samenwerkingsorganisatie worden toegevoegd, mits dit organisatietypen zijn die ook *regionaal openbaar lichaam* zijn met een eigen *bestuurlijk gebied*.

#### Gebieden buiten scope

Niet alle gebieden met een ruimtelijke afbakening passen binnen de huidige scope van dit informatiemodel:

**Verdragsgebieden**

Gebieden waar op basis van internationale verdragen afspraken gelden tussen Nederland en een ander land, zoals het gebied in het [Eems-Dollardverdrag](https://wetten.overheid.nl/BWBV0005343/1978-07-01), vallen buiten scope.

Deze gebieden kenmerken zich doordat:
- Het beheer is verdeeld tussen meerdere landen op basis van een verdrag
- Er geen eenduidig Nederlands regionaal openbaar lichaam is dat er bestuur over uitoefent

Een toekomstige uitbreiding zou een apart objecttype kunnen introduceren voor verdragsgebieden, met verwijzing naar het onderliggende verdrag en de verdeling van verantwoordelijkheden.

**Caribisch Nederland**

De openbare lichamen Bonaire, Sint Eustatius en Saba (BES-eilanden) vallen buiten de huidige scope. Hoewel deze eilanden wel degelijk openbare lichamen zijn met een bestuurlijk gebied, is nader onderzoek nodig voor het verwerken in het conceptueel informatiemodel en de te realiseren voorziening. In een toekomstige versie kunnen de gebieden van Caribisch Nederland worden toegevoegd.

**Wijken en buurten**

Wijken en buurten zijn subgebieden van gemeentegebieden, maar geen bestuurlijke gebieden in de zin van dit informatiemodel. Ze vallen daarom buiten de huidige scope. Wijken en buurten kunnen op termijn als registratieve ruimten worden toegevoegd en gerelateerd worden aan gemeentegebieden.

## Leeswijzer

Puntsgewijs:
 - Hoofdstuk 2: geometrie en levenscyclus van objecten.
 - Hoofdstuk 3: algemene beschrijving van het CIM-BG en de inhoud per onderwerp
 - Hoofdstuk 4: het informatiemodel in detail
 - Tot slot bijlagen en referenties.

In dit document staan ook de gedetailleerde UML-diagrammen. Je kunt op alle diagrammen klikken om in te zoomen en details van de modellen te bekijken.
