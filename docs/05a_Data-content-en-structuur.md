# IMKL informatiemodel


Dit hoofdstuk beschrijft het datamodel van utiliteitsnetten. Aan de hand van UML
klassediagrammen wordt het model beschreven.

## Inleiding


In de volgende paragrafen wordt de inhoud en structuur van het IMKL beschreven
middels UML diagrammen en een bijbehorende objectcatalogus.

Het eerste gedeelte van dit hoofdstuk bevat de UML diagrammen van alle
deelmodellen. Schematisch is opgenomen wat de informatie-inhoud is middels
objecten, hun attributen, datatypen, relaties tussen objecten met alle detail
dat nodig is voor een eenduidige beschrijving. Van elk deelmodel is een compleet
diagram opgenomen waarna in verschillende subparagrafen elke keer een deel in
een apart diagram wordt toegelicht. Sommige onderwerpen hebben een aparte
toelichting nodig; deze worden in de titel aangeduid met ‘Extra toelichting’.

Het tweede gedeelte bevat de objectcatalogus met in tabelvorm dezelfde
informatie als de diagrammen maar nu middels taal beschreven. Alle
informatie-elementen zijn daarbij voorzien van definities en indien nodig een
toelichtende beschrijving. De objectcatalogus bevat de gezamenlijke
informatie-inhoud van alle deelmodellen.

UML diagrammen
---------------

### Beschrijving algemeen principe: IMKL als extensie op INSPIRE

IMKL is gemodelleerd als een extensie op het model voor het INSPIRE thema
Utility and Governmental Services. Binnen dat INSPIRE thema zijn alleen de
modellen voor utiliteitsnetten (utility networks) van belang voor IMKL. IMKL
neemt de hele inhoud over van de INSPIRE specificatie en voegt daar de
specifieke informatie aan toe die nodig is voor realisatie van de in de scope
genoemde processen. Met IMKL kan daardoor een dataset geleverd worden of
dataservice worden ingericht die INSPIRE conform is en voorziet in het detail
van de eisen van de genoemde processen. Er is hierbij opgemerkt dat IMKL als een
modelmatige extensie van de INSPIRE niet betekent dat de in IMKL geleverde data
automatisch INSPIRE data zijn. Dit geldt zeker voor thema’s die niet
INSPIRE-plichtig zijn.

Het volgende diagram geeft de relatie tussen IMKL en de verschillende INSPIRE modellen. IMKL is
een uitbreiding op het INSPIRE Utility Networks model waarin voor de netten
elektriciteit, olie-gas-chemicalien, afvalwater, telecomunicatie, warmte en
drinkwater aparte modellen zijn opgenomen. Deze modellen zijn toepassingen van
het INSPIRE netwerkmodel waarin opgenomen een model voor topologie. Het
netwerkmodel is onderdeel van het INSPIRE Generic Conceptual Model,
basismodellen en basistypen die generiek zijn voor alle INSPIRE thema modellen.
IMKL is een apart pakket met bijbehorende namespace dat gebruik maakt van de
door INSPIRE beheerde pakketten. Een namespace is daarbij gedefinieerd als een
unieke aanduiding voor het domein waarbinnen de informatie-elementen
gedefinieerd zijn. In IMKL zijn afspraken gemaakt over te gebruiken namespaces
en afkortingen hiervoor. De namespace voor IMKL is ‘IMKL’.

<!-- ![](docs/media/IMKL-Klicwin.jpg) -->

<figure id="afb_package-diagram">
    <img src="docs/media/IMKL-Klicwin.jpg" alt="Afbeelding Package diagram">
    <figcaption>Een UML package diagram van de relatie tussen IMKL en de INSPIRE
dataspecificaties. Elk pakket bevat de informatie die op dat niveau wordt
toegevoegd. Het pakket IMKL is een extensie op het INSPIRE model voor Utility
Networks. INSPIRE utilities heeft afhankelijkheden met het INSPIRE algemene
netwerkmodel en INSPIRE basistypen. IMKL omvat het totaal van de aan elkaar
gerelateerde pakketten.</figcaption>
</figure>


### Metamodel

IMKL gebruikt het Metamodel voor Informatiemodellering, MIM. Omdat IMKL een extensie is van het INSPIRE Utility Networks is het INSPIRE metamodel, het INSPIRE Generic
Conceptual Model, ook van toepassing. Beide metamodellen zijn in deze toepassing met elkaar vergelijkbaar.

<!--
voor het beschrijven van de uitbreiding op INSPIRE het zelfde
metamodel voor UML als INSPIRE: het metamodel beschreven in het INSPIRE Generic
Conceptual Model. IMKL wijkt hiermee af van de Nederlandse Standaard voor
informatiemodellering MIM.

De volgende argumenten ondersteunen de keuze voor het INSPIRE metamodel:

\- IMKL is als extensie gemodelleerd op het INSPIRE model. De combinatie van
twee metamodellen maakt de beschrijving van de extensie onnodig complex;

\- Het metamodel van INSPIRE kunnen we niet aanpassen omdat dit in Europees
verband is vastgesteld. -->

De MIM stereotypen worden beschreven in het [Metamodel voor Informatiemodellering, MIM](https://docs.geostandaarden.nl/mim/def-st-mim-20240613/) .
Het INSPIRE metamodel gebruikt de volgende stereotypen.

| **Stereotype**    | **Model element**           | **Beschrijving**                                                                                                               |
|-------------------|-----------------------------|--------------------------------------------------------------------------------------------------------------------------------|
| applicationSchema | Package                     | Een applicatie schema volgens ISO 19109 en NEN 3610.                                                                           |
| featureType       | Class                       | Een geografisch object.                                                                                                        |
| dataType          | Class                       | Een gestructureerd data type zonder identiteit.                                                                                |
| union             | Class                       | Een gestructureerd data type zonder identiteit waarvan precies één van de attributen aanwezig is in een instantie.             |
| enumeration       | Class                       | Gesloten lijst van domeinwaarden.                                                                                              |
| codeList          | Class                       | Open lijst van domeinwaarden                                                                                                   |
| voidable          | Attribute, association role | Om aan te geven dat het attribuut of associatierol een nullwaarde kan hebben. Een reden waarom het attribuut niet ingevuld is. |

### UML - WIBON overzicht

Het onderstaand UML diagram bevat het complete IMKL – WIBON inclusief de relatie
met INSPIRE Utilities. In de hierop volgende paragrafen wordt telkens een deel
van het diagram toegelicht.

**Kleurgebruik in diagrammen:**

-   Oranje: IMKL objecttypen.

-   Rood: INSPIRE Utility Networks per type kabel of leiding

-   Groen en grijs: INSPIRE Utility Networks algemeen

-   Licht oranje en grijs: Niet-instantieerbare objecttypen, datatypen en
    waardelijsten.

-   In de diagrammen onderdelen die gewijzigd zijn ten opzichte van de IMKL 2.0 versie
    met rode kaders aangegeven.

    Voorbeeld: twee toegevoegde attributen:

<!-- ![](docs/media/voorbeeldAangepasteKlasse.png) -->

<figure id="afb_voorbeeldAangepasteklasse">
    <img src="docs/media/voorbeeldAangepasteKlasse.png" alt="Afbeelding voorbeeld aangepaste klasse">
    <figcaption>Voorbeeld van een aangepast objecttype</figcaption>
</figure>

**Link met objectcatalogus.**  
De modelelementen in het UML diagram zijn klikbaar en verwijzen naar de beschrijving van de metagegevens in de objectcatalogus in het hoofdstuk Gegevensdefinitie. 

**Indicatie aanlevering en uitlevering.**  
Voor WIBON geldt dat er een verschil is tussen het dataverkeer tussen de
centrale voorziening en de afnemers, de uitlevering, en het dataverkeer tussen
de netbeheerders en de centrale voorziening, de aanlevering. Bij de
netbeheerders geldt vervolgens dat er een verschil is tussen de centraal
aangesloten netbeheerders en de decentraal aangesloten netbeheerders. Deze
verschillende zijn in de diagrammen aangegeven.

-   Rood omlijnd: gegevens die door de centrale voorziening worden gegenereerd.
    Komen alleen voor in uitlevering.

-   Groen omlijnd: gegevens die voor de centraal aangesloten netbeheerder door
    de voorziening wordt gegenereerd. Decentraal aangesloten netbeheerders
    moeten deze gegevens per melding aan de centrale voorziening leveren.

-   Bij objecttypen is met constraints aangegeven indien er verschil is met
    betrekking tot aan- of uitlevering of een decentraal of centraal aangesloten
    netbeheerder.
	


<div class="imageinfo overview">
<figure><img src="data/Images/EAID_3216E3F5_51CD_42d4_BDBB_F113D31E31A7.png" usemap="#imagemap-EAID_3216E3F5_51CD_42d4_BDBB_F113D31E31A7" alt="Diagram: 01 IMKL-MIM-compleet - overzicht"><figcaption>IMKL: Overzicht model compleet</figcaption>
</figure><map name="imagemap-EAID_3216E3F5_51CD_42d4_BDBB_F113D31E31A7"><area shape="rect" alt="BestandMediaTypeValue" coords="597,618,761,675" href="#global_class_IMKLBasis_BestandMediaTypeValue"><area shape="rect" alt="TopografischObjectTypeValue" coords="399,618,571,675" href="#global_class_IMKLBasis_TopografischObjectTypeValue"><area shape="rect" alt="RioolleidingTypeValue" coords="597,529,761,586" href="#global_class_IMKLBasis_RioolleidingTypeValue"><area shape="rect" alt="NauwkeurigheidDiepteValue" coords="399,536,563,593" href="#global_class_IMKLBasis_NauwkeurigheidDiepteValue"><area shape="rect" alt="LandcodeValue" coords="597,456,761,514" href="#global_class_IMKLBasis_LandcodeValue"><area shape="rect" alt="KleurKabelOfLeidingValue" coords="399,456,563,514" href="#global_class_IMKLBasis_KleurKabelOfLeidingValue"><area shape="rect" alt="Thema" coords="597,380,761,437" href="#global_class_IMKLBasis_Thema"><area shape="rect" alt="InfoKabelbedkabel" coords="14,1669,297,1885" href="#global_class_IMKLBasis_InfoKabelbedkabel"><area shape="rect" alt="Labelpositie" coords="14,1376,275,1498" href="#global_class_IMKLBasis_Labelpositie"><area shape="rect" alt="MaatvoeringsTypeValue" coords="597,301,761,358" href="#global_class_IMKLBasis_MaatvoeringsTypeValue"><area shape="rect" alt="ExtraDetailInfoTypeValue" coords="597,52,761,109" href="#global_class_IMKLBasis_ExtraDetailInfoTypeValue"><area shape="rect" alt="EigenTopografieStatusValue" coords="398,379,562,436" href="#global_class_IMKLBasis_EigenTopografieStatusValue"><area shape="rect" alt="DiepteAangrijpingspuntValue" coords="398,299,562,357" href="#global_class_IMKLBasis_DiepteAangrijpingspuntValue"><area shape="rect" alt="AnnotatieTypeValue" coords="396,215,560,272" href="#global_class_IMKLBasis_AnnotatieTypeValue"><area shape="rect" alt="AchtergrondkaartSoortValue" coords="398,127,562,185" href="#global_class_IMKLBasis_AchtergrondkaartSoortValue"><area shape="rect" alt="LabelpositieValue" coords="596,216,760,273" href="#global_class_IMKLBasis_LabelpositieValue"><area shape="rect" alt="AanvraagSoortValue" coords="398,52,562,109" href="#global_class_IMKLBasis_AanvraagSoortValue"><area shape="rect" alt="Achtergrondkaart" coords="14,1249,347,1371" href="#global_class_IMKLBasis_Achtergrondkaart"><area shape="rect" alt="Organisatie" coords="15,935,349,1222" href="#global_class_LeveringGebiedsinformatie_Organisatie"><area shape="rect" alt="Opdrachtgever" coords="15,789,349,928" href="#global_class_LeveringGebiedsinformatie_Opdrachtgever"><area shape="rect" alt="Contact" coords="15,625,349,782" href="#global_class_LeveringGebiedsinformatie_Contact"><area shape="rect" alt="Aanvrager" coords="15,226,349,383" href="#global_class_LeveringGebiedsinformatie_Aanvrager"><area shape="rect" alt="AanvraagSoortContact" coords="15,44,349,219" href="#global_class_LeveringGebiedsinformatie_AanvraagSoortContact"><area shape="rect" alt="Adres" coords="15,390,349,618" href="#global_class_IMKLBasis_Adres"><area shape="rect" alt="NEN3610ID" coords="14,1516,347,1655" href="#global_class_IMKLBasis_NEN3610ID"><area shape="rect" alt="Beheerder" coords="2599,287,2886,450" href="#global_class_LeveringGebiedsinformatie_Beheerder"><area shape="rect" alt="Overig" coords="1583,1290,1719,1386" href="#global_class_IMKLBasis_Overig"><area shape="rect" alt="Belanghebbende" coords="2066,257,2431,395" href="#global_class_LeveringGebiedsinformatie_Belanghebbende"><area shape="rect" alt="TechnischGebouw" coords="3342,1322,3562,1417" href="#global_class_IMKLBasis_TechnischGebouw"><area shape="rect" alt="BuisSpecifiek" coords="966,1030,1357,1134" href="#global_class_IMKLBasis_BuisSpecifiek"><area shape="rect" alt="EisVoorzorgsmaatregelBijlage" coords="1645,139,1975,332" href="#global_class_IMKLBasis_EisVoorzorgsmaatregelBijlage"><area shape="rect" alt="ExtraInformatie" coords="1563,444,1790,589" href="#global_class_IMKLBasis_ExtraInformatie"><area shape="rect" alt="Leidingelement" coords="2886,716,3276,913" href="#global_class_IMKLBasis_Leidingelement"><area shape="rect" alt="KabelEnLeidingContainer" coords="1820,1032,2221,1218" href="#global_class_IMKLBasis_KabelEnLeidingContainer"><area shape="rect" alt="ExtraGeometrie" coords="1937,670,2224,845" href="#global_class_IMKLBasis_ExtraGeometrie"><area shape="rect" alt="Maatvoering" coords="851,537,1177,697" href="#global_class_IMKLBasis_Maatvoering"><area shape="rect" alt="AanduidingEisVoorzorgsmaatregel" coords="1443,649,1818,887" href="#global_class_IMKLBasis_AanduidingEisVoorzorgsmaatregel"><area shape="rect" alt="Mantelbuis" coords="1745,1290,1990,1451" href="#global_class_IMKLBasis_Mantelbuis"><area shape="rect" alt="Kabelbed" coords="2267,1211,2502,1337" href="#global_class_IMKLBasis_Kabelbed"><area shape="rect" alt="KabelOfLeiding" coords="851,757,1252,947" href="#global_class_IMKLBasis_KabelOfLeiding"><area shape="rect" alt="Diepte" coords="2307,772,2776,965" href="#global_class_IMKLBasis_Diepte"><area shape="rect" alt="Telecommunicatiekabel" coords="640,1292,827,1387" href="#global_class_IMKLBasis_Telecommunicatiekabel"><area shape="rect" alt="Elektriciteitskabel" coords="489,1292,623,1384" href="#global_class_IMKLBasis_Elektriciteitskabel"><area shape="rect" alt="KabelSpecifiek" coords="532,1032,763,1136" href="#global_class_IMKLBasis_KabelSpecifiek"><area shape="rect" alt="Label" coords="2948,48,3238,169" href="#global_class_IMKLBasis_Label"><area shape="rect" alt="IMKLBasis" coords="2948,190,3238,332" href="#global_class_IMKLBasis_IMKLBasis"><area shape="rect" alt="DiepteNAP" coords="2373,1032,2713,1153" href="#global_class_IMKLBasis_DiepteNAP"><area shape="rect" alt="DiepteTovMaaiveld" coords="2045,925,2180,996" href="#global_class_IMKLBasis_DiepteTovMaaiveld"><area shape="rect" alt="ContainerLeidingelement" coords="2949,1032,3430,1211" href="#global_class_IMKLBasis_ContainerLeidingelement"><area shape="rect" alt="Kast" coords="3184,1322,3307,1417" href="#global_class_IMKLBasis_Kast"><area shape="rect" alt="Mangat" coords="3027,1322,3150,1417" href="#global_class_IMKLBasis_Mangat"><area shape="rect" alt="Mast" coords="2873,1322,2996,1417" href="#global_class_IMKLBasis_Mast"><area shape="rect" alt="Toren" coords="2713,1322,2836,1417" href="#global_class_IMKLBasis_Toren"><area shape="rect" alt="Appurtenance" coords="2502,1322,2679,1443" href="#global_class_IMKLBasis_Appurtenance"><area shape="rect" alt="Duct" coords="2045,1290,2221,1386" href="#global_class_IMKLBasis_Duct"><area shape="rect" alt="ThermischePijpleiding" coords="1404,1292,1565,1394" href="#global_class_IMKLBasis_ThermischePijpleiding"><area shape="rect" alt="Waterleiding" coords="1268,1292,1391,1387" href="#global_class_IMKLBasis_Waterleiding"><area shape="rect" alt="Rioolleiding" coords="1091,1292,1252,1387" href="#global_class_IMKLBasis_Rioolleiding"><area shape="rect" alt="OlieGasChemicalienPijpleiding" coords="853,1292,1077,1387" href="#global_class_IMKLBasis_OlieGasChemicalienPijpleiding"><area shape="rect" alt="Utiliteitsnet" coords="2127,467,2561,611" href="#global_class_IMKLBasis_Utiliteitsnet"><area shape="rect" alt="Annotatie" coords="851,328,1177,485" href="#global_class_IMKLBasis_Annotatie"><area shape="rect" alt="ExtraDetailinfo" coords="853,52,1178,284" href="#global_class_IMKLBasis_ExtraDetailinfo"><area shape="rect" alt="EigenTopografie" coords="2066,41,2431,202" href="#global_class_IMKLBasis_EigenTopografie"><area shape="rect" alt="OverigSpecifiek" coords="1430,1030,1686,1170" href="#global_class_IMKLBasis_OverigSpecifiek"></map>            
         </div>        
	
	

<!-- ![](docs/media/1.IMKL-Model-compleet.png) -->
<!--
<figure id="afb_IMKL-model-compleet">
    <img src="docs/media/1.IMKL-Model-compleet.png" alt="Afbeelding IMKL model compleet">
    <figcaption>IMKL: Overzicht model compleet</figcaption>
</figure>
-->

Toelichting bij het diagram.

Het UML diagram brengt het IMKL – WIBON voor netinformatie inclusief de relatie
met INSPIRE in beeld. De specifiek voor de andere deelmodellen opgenomen
informatie zit hier nog niet in. Ook de WIBON gebiedsinformatie, graafpolygoon
en belangenregistratie zijn niet opgenomen (zie daarvoor paragraaf [WIBON uitleveren van gebiedsinformatie](#wibon-uitleveren-van-gebiedsinformatie)). Voor
de leesbaarheid zijn een aantal relaties niet opgenomen. In de detaildiagrammen
komen die wel terug. Met omlijningen zijn onderdelen van het diagram benoemd:
IMKL en INSPIRE Generic Network Model. Aan de bovenzijde bevindt zich de IMKL
toevoeging op het INSPIRE Utilities model. Aan de onderzijde het INSPIRE
Utilities model. De koppelingslaag is via de IMKL objecttypen die zich in het
midden bevinden: Elektriciteitskabel, Telecommunicatiekabel, Waterleiding tot en
met TechnischGebouw. Deze objecttypen zijn 1 op 1 gerelateerd aan de overeenkomstige
objecttypen uit INSPIRE Utilities. IMKL:Elektricteitskabel aan
INSPIRE:ElectricityCable, IMKL:Waterleiding aan INSPIRE:WaterPipe enz. Ze
bevatten daarmee alle INSPIRE eigenschappen en relaties van die objecttypen. De
IMKL koppelingslaag is ook gekoppeld aan de IMKL inhoudelijke informatie. Deze
is gemodelleerd in de objecttypen KabelOfLeiding, Leidingelement en de
containerversies van beide.

De objecttypen in de IMKL koppelingslaag (Elektricteitskabel, Waterleiding enz)
vormen de centrale objecten in een IMKL dataset. Via overerving en relaties
worden alle eigenschappen toegevoegd, hetzij van de INSPIRE zijde van het model,
hetzij van de IMKL zijde van het model. Als voorbeeld het attribuut geometrie
van een waterleiding. Deze is gedefinieerd als centreLineGeometry bij het
objecttype Link uit het Generic Network Model. Via UtilityLinkSet wordt dat
overgeërfd door het objecttype Pipe, vervolgens doorgegeven aan WaterPipe
waardoor het bij de IMKL waterleiding komt. Een ander voorbeeld is het attribuut
UtilityDeliveryType bij het INSPIRE objecttype UtilityLinkSet. Overerving is
door alle kabel-, buis- en ducttypen.

### Associaties in het model

In het model zijn associaties opgenomen om de relatie tussen objecttypen te
benoemen. In het IMKL gedeelte zijn regels opgenomen voor het bepalen van de
richting waarin de associaties zijn bepaald:

-   Elke associatie wijst één kant op. Er zijn dus geen inverse associaties. Als
    er een verwijzing naar beide kanten nodig is worden er twee associaties
    opgenomen;

-   Elk objecttype in IMKL verwijst direct naar het utiliteitsnet waar het bij
    hoort. Dit gebeurt in alle gevallen met een associatierol genaamd inNetwork.
    Dat geldt ook voor objecttypen als Annotatie, Maatvoering, Bijlage en
    dergelijke. Informatie technisch is het mogelijk dat sommige objecttypen bij
    meerdere utiliteitsnetten horen, bijvoorbeeld een door verschillende netten
    gedeelde mantelbuis, of een dieptemarkering. De associatierol inNetwork is
    daarom 1..\*. Echter vanuit operationeel punt bezien is dat niet wenselijk.
    Met een constraint (‘Max1Utiliteitsnet’) is daarom in alle gevallen het
    maximaal aantal utiliteitsnetten waarnaar verwezen kan worden beperkt tot 1.

-   Voor netwerkelementen geldt dat associaties verwijzen naar de objecten
    ExtraInformatie en Diepte die er bij horen en niet andersom.

### Numerieke waarden

Numerieke waarden bij attributen worden opgenomen conform de bij het attribuut
opgegeven eenheid en nauwkeurigheid. Indien de waarde als label is opgenomen en
dus een alfanumeriek datatype heeft geldt de komma als decimaal scheidingsteken.
Voor de in specifieke datatypen gedefinieerde waarden geldt een punt als het
afgesproken decimaal scheidingsteken. De specifieke datatypen voor waarden zoals
Measure bestaan uit een combinatie van een waarde en een eenheid.

### Waardelijsten zijn extern

De opgenomen waardelijsten van het type  «Codelijst» worden niet in het UML
beheerd maar in externe waardelijsten. Zij worden gepubliceerd in een
waardelijstregister. Ze maken wel onderdeel uit van IMKL maar omdat ze
dynamischer zijn voor wat betreft het inhoudelijk beheer zijn ze uit de UML
beschrijving gehaald.

### Basisattributen voor identificatie en labels

Identificatie: Alle concrete objecttypen en daarmee objecten in een dataset
hebben een attribuut voor identificatie. Met deze identificatie kunnen ze uniek
geïdentificeerd worden. INSPIRE gebruikt hiervoor het attribuut identifier met
het datatype Identifier. Veel objecttypen uit IMKL overerven die attributen.
Voor objecttypen die specifiek voor IMKL zijn gecreëerd en die niet via een
generalisatie aan INSPIRE zijn gekoppeld is er een attribuut identificatie met
het datatype NEN3610ID. Zie ook paragraaf [Identifier management](#identifier-management).

Label: Label is een abstract datatype dat is gecreëerd om middels overerving aan
bijna alle objecten een mogelijkheid voor het toekennen van een label te bieden.
Merk op dat voor annotatie en maatvoering (ExtraInformatie) en diepte,
bijbehorende labels via het object Label doorgegeven worden. Het af te beelden
label (getal of tekst) wordt opgenomen bij het attribuut label. Vanuit praktisch
punt is het maximaal aantal karakters van een label op 40 gezet. In het
attribuut omschrijving kan een betekenis worden opgenomen. Bij de subklassen
Maatvoering, Annotatie en Diepte is het plaatsingspunt van een label bepaald met
een attribuut ligging. Bij andere subklassen, bijvoorbeeld de netelementen wordt
de plaatsing van een eventueel label in een viewer bepaald.

**Voidable:** Bij attributen en associaties die het stereotype «voidable»
hebben kan, indien het van toepassing is, geen waarde worden ingevuld. Optioneel
kan er ook een reden opgenomen worden waarom er geen waarde is ingevuld. De
benoemde redenen zijn:

**Unknown:** Waarde onbekend: De waarde is bij de zender niet bekend.

**Unpopulated:** Niet ondersteund: De zender houdt in zijn registratie geen
waarde voor dit attribuut bij. Geldt voor alle objecten van dit objecttype.

**Withheld:** Niet geautoriseerd: De zender vindt dat de ontvanger niet
geautoriseerd is om de waarde te kennen. Waarde is vertrouwelijk en wordt niet uitgewisseld.

 <div class="imageinfo ">
            <figure><img src="data/Images/EAID_E4F35B46_D606_4b8e_8EB1_EB4DD5A20A4D.png" usemap="#imagemap-EAID_E4F35B46_D606_4b8e_8EB1_EB4DD5A20A4D" alt="Diagram: 02.IMKL-Basisinformatie - detail"><figcaption>Basistypen van het model: Identificatie en label. Alle objecttypen
hebben verplicht een identifier. Bijna alle objecten hebben optioneel een label.</figcaption>
            </figure><map name="imagemap-EAID_E4F35B46_D606_4b8e_8EB1_EB4DD5A20A4D"><area shape="rect" alt="EisVoorzorgsmaatregelBijlage" coords="14,1067,280,1148" href="#global_class_IMKLBasis_EisVoorzorgsmaatregelBijlage"><area shape="rect" alt="Label" coords="992,380,1220,555" href="#global_class_IMKLBasis_Label"><area shape="rect" alt="ExtraGeometrie" coords="543,485,742,574" href="#global_class_IMKLBasis_ExtraGeometrie"><area shape="rect" alt="ExtraInformatie" coords="563,692,845,780" href="#global_class_IMKLBasis_ExtraInformatie"><area shape="rect" alt="Diepte" coords="711,842,992,931" href="#global_class_IMKLBasis_Diepte"><area shape="rect" alt="ContainerLeidingelement" coords="1346,675,1628,764" href="#global_class_IMKLBasis_ContainerLeidingelement"><area shape="rect" alt="Leidingelement" coords="1346,547,1628,636" href="#global_class_IMKLBasis_Leidingelement"><area shape="rect" alt="KabelEnLeidingContainer" coords="1346,396,1628,485" href="#global_class_IMKLBasis_KabelEnLeidingContainer"><area shape="rect" alt="KabelOfLeiding" coords="1346,253,1628,342" href="#global_class_IMKLBasis_KabelOfLeiding"><area shape="rect" alt="Utiliteitsnet" coords="1346,115,1628,204" href="#global_class_IMKLBasis_Utiliteitsnet"><area shape="rect" alt="EigenTopografie" coords="813,27,1103,116" href="#global_class_IMKLBasis_EigenTopografie"><area shape="rect" alt="IMKLBasis" coords="574,217,883,357" href="#global_class_IMKLBasis_IMKLBasis"><area shape="rect" alt="Orientatiepolygoon" coords="14,951,280,1026" href="#global_class_LeveringGebiedsinformatie_Orientatiepolygoon"><area shape="rect" alt="Informatiepolygoon" coords="14,849,280,924" href="#global_class_LeveringGebiedsinformatie_Informatiepolygoon"><area shape="rect" alt="Graafpolygoon" coords="14,742,280,817" href="#global_class_LeveringGebiedsinformatie_Graafpolygoon"><area shape="rect" alt="Beheerder" coords="14,636,280,711" href="#global_class_LeveringGebiedsinformatie_Beheerder"><area shape="rect" alt="Belanghebbende" coords="14,526,280,601" href="#global_class_LeveringGebiedsinformatie_Belanghebbende"><area shape="rect" alt="GebiedsinformatieAanvraag" coords="14,422,280,497" href="#global_class_LeveringGebiedsinformatie_GebiedsinformatieAanvraag"><area shape="rect" alt="BelangGeneriek" coords="14,321,280,396" href="#global_class_LeveringGebiedsinformatie_BelangGeneriek"><area shape="rect" alt="GebiedsinformatieLevering" coords="14,217,280,292" href="#global_class_LeveringGebiedsinformatie_GebiedsinformatieLevering"></map>
         </div>

<!-- ![](docs/media/2.IMKL-Basisinformatie.png) -->
<!--
<figure id="afb_2.IMKL-Basisinformatie">
    <img src="docs/media/2.IMKL-Basisinformatie.png" alt="Afbeelding Basisinformatie">
    <figcaption>Basistypen van het model: Identificatie en label. Alle objecttypen
hebben verplicht een identifier. Bijna alle objecten hebben optioneel een label.</figcaption>
</figure>
-->
<!--Figuur 5.2: Basistypen van het model: Identificatie en label. Alle objecttypen
hebben verplicht een identifier. Bijna alle objecten hebben optioneel een label. -->

LifespanVersion: In de basistypen van het model zitten twee attributen voor een
temporeel model: beginLifesepanVersion en endLifespanVersion. INSPIRE kent die
attributen ook en past die toe bij het objecttype NetwerkElement. In IMKLBasis
zijn ze toegevoegd voor die objecttypen die niet van INSPIRE overerven.
beginLifespanVersion is daarin de begindatum waarop deze versie van een data
object in de registratie werd aangemaakt of veranderd; het begin van de
levenscyclus van deze versie van een data object. endLifespanVersion is de datum
die het einde van een levenscyclus van deze versie van een data object aangeeft;
het moment vanaf wanneer het geen onderdeel meer is van de actuele registratie.
Zie ook paragraaf [Tijd representatie en temporeel model](#tijd-representatie-en-temporeel-model).

### IMKL semantische kern

De kern van het IMKL model bevat de semantiek van de extra informatie voor de
Nederlandse gebruikstoepassingen. Alleen de objecttypen die de inhoudelijke IMKL
informatie bevatten en die extra aan het INSPIRE Utility networks model zijn
toegevoegd zijn afgebeeld. Bijvoorbeeld geometrie en netwerktopologie zitten in
INSPIRE Utility networks en zijn niet afgebeeld.

<div class="imageinfo ">
            <figure><img src="data/Images/EAID_D6B443A2_47FB_409b_98A7_C129F2EEBB2C.png" usemap="#imagemap-EAID_D6B443A2_47FB_409b_98A7_C129F2EEBB2C" alt="Diagram: 03.IMKL-Semantische-kern - detail"><figcaption>IMKL semantische kern voor WIBON toepassing. Een utiliteitsnet
bestaat uit elementen. De elementen hebben attributen en een link met extra
informatie.</figcaption>
            </figure><map name="imagemap-EAID_D6B443A2_47FB_409b_98A7_C129F2EEBB2C"><area shape="rect" alt="NauwkeurigheidXYvalue" coords="1793,694,2024,767" href="#global_class_IMKLBasis_NauwkeurigheidXYvalue"><area shape="rect" alt="BestandMediaTypeValue" coords="22,500,231,585" href="#global_class_IMKLBasis_BestandMediaTypeValue"><area shape="rect" alt="Adres" coords="417,14,707,242" href="#global_class_IMKLBasis_Adres"><area shape="rect" alt="Appurtenance" coords="1825,1300,2043,1497" href="#global_class_IMKLBasis_Appurtenance"><area shape="rect" alt="Contact" coords="884,1446,1089,1585" href="#global_class_LeveringGebiedsinformatie_Contact"><area shape="rect" alt="Annotatie" coords="22,619,257,883" href="#global_class_IMKLBasis_Annotatie"><area shape="rect" alt="Maatvoering" coords="14,1158,295,1421" href="#global_class_IMKLBasis_Maatvoering"><area shape="rect" alt="AanduidingEisVoorzorgsmaatregel" coords="629,1095,953,1421" href="#global_class_IMKLBasis_AanduidingEisVoorzorgsmaatregel"><area shape="rect" alt="ExtraInformatie" coords="767,754,1020,918" href="#global_class_IMKLBasis_ExtraInformatie"><area shape="rect" alt="ContainerLeidingelement" coords="1245,1584,1622,1870" href="#global_class_IMKLBasis_ContainerLeidingelement"><area shape="rect" alt="Leidingelement" coords="1245,1275,1622,1561" href="#global_class_IMKLBasis_Leidingelement"><area shape="rect" alt="KabelEnLeidingContainer" coords="1245,1003,1622,1253" href="#global_class_IMKLBasis_KabelEnLeidingContainer"><area shape="rect" alt="KabelOfLeiding" coords="1245,728,1622,979" href="#global_class_IMKLBasis_KabelOfLeiding"><area shape="rect" alt="EisVoorzorgsmaatregelBijlage" coords="779,14,1100,282" href="#global_class_IMKLBasis_EisVoorzorgsmaatregelBijlage"><area shape="rect" alt="Utiliteitsnet" coords="1245,409,1622,694" href="#global_class_IMKLBasis_Utiliteitsnet"><area shape="rect" alt="EigenTopografie" coords="1785,14,2122,264" href="#global_class_IMKLBasis_EigenTopografie"><area shape="rect" alt="Belanghebbende" coords="1238,14,1525,317" href="#global_class_LeveringGebiedsinformatie_Belanghebbende"><area shape="rect" alt="ExtraDetailinfo" coords="22,14,353,358" href="#global_class_IMKLBasis_ExtraDetailinfo"><area shape="rect" alt="LabelpositieValue" coords="629,1457,860,1529" href="#global_class_IMKLBasis_LabelpositieValue"><area shape="rect" alt="Thema" coords="1793,571,2024,644" href="#global_class_IMKLBasis_Thema"><area shape="rect" alt="MaatvoeringsTypeValue" coords="22,1480,253,1553" href="#global_class_IMKLBasis_MaatvoeringsTypeValue"><area shape="rect" alt="AnnotatieTypeValue" coords="22,918,253,991" href="#global_class_IMKLBasis_AnnotatieTypeValue"><area shape="rect" alt="ExtraDetailInfoTypeValue" coords="22,409,231,493" href="#global_class_IMKLBasis_ExtraDetailInfoTypeValue"><area shape="rect" alt="EigenTopografieStatusValue" coords="1793,454,2024,526" href="#global_class_IMKLBasis_EigenTopografieStatusValue"></map>
         </div>

<!--![](docs/media/3.IMKL-Semantische-kern.png) -->


<!--Figuur 5.3: IMKL semantische kern voor WIBON toepassing. Een utiliteitsnet
bestaat uit elementen. De elementen hebben attributen en een link met extra
informatie.-->
<!--
<figure id="afb_3.IMKL-Semantische-kern">
    <img src="docs/media/3.IMKL-Semantische-kern.png" alt="Afbeelding Semantische kern">
    <figcaption>IMKL semantische kern voor WIBON toepassing. Een utiliteitsnet
bestaat uit elementen. De elementen hebben attributen en een link met extra
informatie.</figcaption>
</figure>
-->
Toelichting bij het diagram: Een Utiliteitsnet bestaat uit objecten
KabelOfLeiding, Leidingelement, KabelEnLeidingContainer en
ContainerLeidingelement. Via het associatie attribuut inNetwork worden deze
gerefereerd aan één Utiliteitsnet van één thema. Deze associatie is alleen
zichtbaar bij ContainerLeidingelement. De andere netwerkobjecten hebben die
associatie via het INSPIRE Netwerk model. Alle objecten hebben kenmerken. De
objecttypen kunnen uitgebreid worden met ExtraInformatie. Dit kan annotatie,
maatvoering en/of extra bestanden zijn. Al deze typen vallen onder de
superklasse ExtraInformatie en worden vanuit de andere objecten gerefereerd via
het attribuut heeftExtraInformatie. Omdat alle elementen van en in een
Utiliteitsnet middels het associatie attribuut inNetwork refereren aan het
Utiliteitsnet is typering van alle elementen mogelijk op waarden van het
attribuut thema. Alle elementen kunnen daarmee per thema geselecteerd worden.

**Maximaal 1 utiliteitsnet per netelement.**

ContainerLeidingelementen en KabelEnLeidingContainers (Kabelbed, Mantelbuis en
Duct) kunnen in de werkelijkheid bij meerdere utiliteitsnetten geregistreerd
zijn. Dat geldt dan natuurlijk ook voor objecten die daaraan zijn geassocieerd,
zoals ExtraInformatie en Diepte. Het IMKL model dwingt met een aparte constraint
(Max1Utiliteitsnet) af dat in de datauitwisseling een netelement altijd naar
maximaal 1 utiliteitsnet kan verwijzen. Het kan daarmee voorkomen dat in een
totaalset van een WIBON uitlevering elementen dubbel zijn opgenomen.
Bijvoorbeeld een gedeelde mantelbuis komt zowel in het telecomnet als in het
waternet voor.

Een Utiliteitsnet wordt gerefereerd door een Belanghebbende, deze heeft een
belang in een WIBON aanvraag. De Belanghebbende kan verwijzen naar een object
EigenTopografie voor het koppelen van een extra toegevoegde topografie.

**Extra toelichting: ExtraDetailinfo, maatvoering, annotatie.**

Een utiliteitsnet of individuele netelementen kunnen via het attribuut
heeftExtraInformatie verwijzen naar extra informatie van toepassing op dat
element. Extra informatie kan in de vorm een gekoppeld bestand, maatvoering,
annotatie of een eis voorzorgsmaatregel.

Annotatie:

Pijlen, lijnen en labels die als annotatie op een kaartbeeld staan en niet als
maatvoering gelden worden met het object Annotatie opgenomen. Met het attribuut
ligging wordt de geometrie van de annotatie aangegeven of de plaatsingspunt van
het label. De tekst en eventueel betekenis van het label worden via het object
Label opgenomen.

Het uitwisselen van annotatie gebeurt alleen daar waar de bronhouder het nodig
vindt om deze informatie als annotatie op te nemen. Annotatie objecten zijn
zelfstandige objecten die middels een associatie aan een Utiliteitsnet zijn
verbonden en optioneel ook gerefereerd worden door het netelement waar ze
betrekking op hebben. Annotatie bevat in veel gevallen de informatie die ook bij
de netelementen zelf opgenomen kan worden maar in de bronbestanden niet als
gekoppelde informatie is opgenomen. De verwachting is dat het gebruik van
annotatie als bron van informatie in de toekomst afneemt en de object gekoppelde
en opvraagbare informatie toeneemt.

ExtraDetailinfo:

Extra detailinformatie in de vorm van bestanden kan optioneel aan een
utiliteitsnet of netelement worden gekoppeld via het attribuut
heeftExtraInformatie. Bestanden kunnen verschillende typen informatie
beschrijven zoals een aansluiting, huisaansluiting of een profielschets met een
lengte- of dwarsprofiel (zie ook paragraaf [Leidingelement](#leidingelement)). Het bestandstype moet worden
gespecificeerd en is in alle gevallen pdf.

Met het verplichte attribuut ligging wordt de locatie aangegeven waar de
detailinformatie van toepassing is. In een viewer kan die locatie dan
gevisualiseerd worden.

Maatvoering:

Maatvoering wordt gebruikt om de positie van een netwerkelement ten opzichte van
aanwezige bebouwing weer te geven. Als maatvoering is opgenomen dan zijn die
gegevens leidend irt de afstanden die uit de coördinaten berekend kunnen worden.
De annotatietypen voor maatvoering zijn: maatvoeringshulplijn, maatvoeringslijn,
maatvoeringspijl, maatvoeringspijlpunt of maatvoeringslabel. Een
maatvoeringspijlpunt wordt middels een puntsymbool uitgewisseld.


| **Waarde**   | **Omschrijving**                                                                                     |
|---------------|------------------------------------------------------------------------------------------------------|
| maatvoeringshulplijn | Lijn om een hulplijn in een maatvoering te visualiseren                                              |
| maatvoeringslijn | Lijn om een lijn in een maatvoering te visualiseren                                                  |
| maatvoeringslabel | Punt en label om een label in een maatvoering te visualiseren                                        |
| maatvoeringspijlpunt | Punt om een pijlpunt in een maatvoering te visualiseren. Is een punt met een bijbehorend puntsymbool |
| maatvoeringspijl | Lijn met aan beide kanten een pijlpunt                                                               |


Elke maatvoeringslijn wordt een apart object.

Het maatvoeringslabel geeft met een label-attribuut het label aan dat als
maatvoeringsgetal wordt afgebeeld. Bijvoorbeeld ‘25’. Overeenkomstig NEN 3116 is
de eenheid meter en de gebruikelijke nauwkeurigheid is 0,1. Het decimale
scheidingsteken is een komma. Het attribuut label wordt via het object
ExtraInformatie overerft van het object Label. In het attribuut omschrijving van
het object Label kan indien nodig een nadere omschrijving worden opgenomen, zie
[Figuur IMKL-Basisinformatie](#afb_2.IMKL-Basisinformatie). De locatie van het label en de geometrie van de maatvoeringslijnen
wordt met het attribuut ligging opgenomen. Maatvoering is direct gekoppeld aan
een Utiliteitsnet. Hierdoor kan middels het thema attribuut van Utiliteitsnet de
maatvoering per thema worden geselecteerd.

**Extra toelichting: Eis voorzorgsmaatregel en Bijlage.**

Een eis voorzorgsmaatregel geeft aan dat de beheerder van een net aangegeven
heeft dat er sprake is van voorzorgsmaatregelen die getroffen dienen te worden.
Dit betreft alleen de wettelijk geregelde eis voorzorgsmaatregel. Bij een WIBON
uitlevering wordt – per thema - de voorzorgsmaatregel met de hoogste prioriteit
bijgesloten middels een gekoppeld separaat bestand beschreven in
EisVoorzorgsmaatregelBijlage. Van deze bijlage wordt vastgelegd op welk thema
deze betrekking heeft en de te nemen eis voorzorgsmaatregel. De bijlage behoort
bij een Belanghebbende netbeheerder. Op het niveau van de individuele
netelementen is de eis voorzorgsmaatregel aangegeven via een object
AanduidingEisVoorzorgsmaatregel. In dat geval is het netelement en of de locatie
aangegeven waar een voorzorgsmaatregel geldt.

Standaard wordt de geometrie van het object AanduidingEisVoorzorgsmaatregel
gebruikt om aan te geven op welke kabel of leiding of deel daarvan een
voorzorgsmaatregel van toepassing is. De begrenzing van de geometrie is dan om
dit te visualiseren en eenvoudig ruimtelijke selecteerbaar te maken.

De aanduiding van een eis voorzorgsmaatregel is functioneel gerelateerd aan een
kabel of leiding maar een directe informatiekundige associatie tussen een kabel
of leiding en de AanduidingEisVoorzorgsmaatregel is niet verplicht. De
strookbreedte die de netbeheerder voor het betreffende object wil hanteren wordt
door de netbeheerder als vlakgeometrie aangeleverd bij de aanduiding eis
voorzorgsmaatregel.

De toepassing van eis voorzorgsmaatregelen en het gebied waarop deze betrekking
heeft, is een verantwoordelijkheid van de netbeheerder en wordt door de
netbeheerder zelf bepaald.

Voor de geometrie van aanduidingen eis voorzorgsmaatregel zijn ook multivlakken
toegestaan.

Naast de bijlage voor de eis voorzorgsmaatregel is er in het IMKL ook nog een
mogelijkheid om als netbeheerder een algemene bijlage mee te leveren bij de
gebiedsinformatielevering.

In het kader van de reductie van het aantal bijlagen, wordt aangemoedigd om deze
algemene informatie als URL beschikbaar te stellen (attribuut websiteKLIC).

**Extra toelichting: EigenTopografie.**

Indien er extra topografie nodig is om de positie van netwerkelementen nader aan
te geven kan dit middels het object EigenTopografie. Er kan een bestaande - of
plan-topografie worden meegegeven. Met het attribuut ligging wordt de geometrie
van de EigenTopografie opgenomen. De eigen topografie wordt altijd
gevectoriseerd aangeleverd. De topografische elementen worden getypeerd conform
een typeringslijst TopografischObjectTypeValue, gebaseerd op IMGeo. Hiermee is
het type topografisch object omschreven en is een koppeling met
visualisatieregels mogelijk.

### Geometrie en topologie

**2D geometrie:**

Het verplichte geometrieprofiel van IMKL is 2D. Primair bestaat de geometrie uit
punten en lijnen die het netwerk representeren. 2D vlakken zijn additioneel
waarbij ook multivlakken zijn toegestaan. 2,5 D en 3D zijn een additionele
extensie.

 <div class="imageinfo ">
            <figure><img src="data/Images/EAID_2DB1F473_2642_462e_BF36_E72294DE24EE.png" usemap="#imagemap-EAID_2DB1F473_2642_462e_BF36_E72294DE24EE" alt="Diagram: 04.IMKL-Geometrie - detail"><figcaption>Geometriemodel. Primair en verplicht punten en (hart)lijnen.
Optioneel vlakken en additioneel 3D.</figcaption>
            </figure><map name="imagemap-EAID_2DB1F473_2642_462e_BF36_E72294DE24EE"><area shape="rect" alt="ContainerLeidingelement" coords="323,359,655,540" href="#global_class_IMKLBasis_ContainerLeidingelement"><area shape="rect" alt="Leidingelement" coords="227,551,559,713" href="#global_class_IMKLBasis_Leidingelement"><area shape="rect" alt="KabelEnLeidingContainer" coords="128,728,461,864" href="#global_class_IMKLBasis_KabelEnLeidingContainer"><area shape="rect" alt="KabelOfLeiding" coords="33,891,365,1054" href="#global_class_IMKLBasis_KabelOfLeiding"><area shape="rect" alt="Utiliteitsnet" coords="518,22,791,308" href="#global_class_IMKLBasis_Utiliteitsnet"><area shape="rect" alt="ExtraGeometrie" coords="51,14,365,299" href="#global_class_IMKLBasis_ExtraGeometrie"></map>
         </div>

<!-- ![](docs/media/4.IMKL-Geometrie.png) -->

<!--Figuur 5.4: Geometriemodel. Primair en verplicht punten en (hart)lijnen.
Optioneel vlakken en additioneel 3D. -->
<!--
<figure id="afb_4.IMKL-Geometrie.png">
    <img src="docs/media/4.IMKL-Geometrie.png" alt="Afbeelding Geometrie">
    <figcaption>Geometriemodel. Primair en verplicht punten en (hart)lijnen.
Optioneel vlakken en additioneel 3D.</figcaption>
</figure>
-->
De geometrie van de netwerkelementen wordt overgeërfd uit het Inspire Netwerk
model. Alle netwerkelementen zijn onderdeel van een topologisch netwerk en
worden geometrisch beschreven door links of nodes. De geometrieën zijn verplicht
punten of lijnen. Lijnen kunnen opgebouwd zijn uit meerdere lijnsegmenten. De
lijnen en punten zijn niet schematisch (niet ‘fictitious’) en representeren de
locatie van de netwerkelementen middels hartlijnen. Lijnen van leidingen en
punten van bijbehorende leidingelementen hoeven niet noodzakelijkerwijs aan te
sluiten. De connectiviteit wordt gerealiseerd door de arc-node topologie. Als
voorbeeld een pompstation in een rioolnetwerk. Het door een (center) punt
gerepresenteerde pompstation is niet verbonden met leidingen. Er lopen wel
leidingen naar de punt toe maar niet tot aan de punt. De leidingen hebben wel
een verwijzing naar de node (connectiviteit).

Additioneel en optioneel kan een netwerkelement ook nog een vlak als geometrie
hebben, een verwijzing naar een object ExtraGeometrie middels een relatie
extraGeometrie. Indien het pompstation ook nog door een vlak wordt
gerepresenteerd lopen de leidingen in de regel wel tot aan de begrenzing van het
vlak.

Lijnen zijn in het INSPIRE netwerkmodel gemodelleerd als een LinkSet die bestaat
uit een verzameling van 1 of meer GeneralisedLinks. Dit kunnen Links zijn van
het type Curve of een LinkSequence, een geordende verzameling DirectedLinks. De
LinkSequence kan worden toegepast als er een route, met een richting,
uitgewisseld moet worden. Voor IMKL is dit niet relevant en wordt de
LinkSequence derhalve niet toegepast

Meervoudig gebruik van geometrieën is niet toegestaan.

In principe staat het INSPIRE model toe dat een link door meerdere
netwerkelementen wordt gebruikt. In de IMKL uitwisseling is dat echter niet
toegestaan. Elke link wordt maar door één netwerkelement gebruikt.

Het ruimtelijke referentiesysteem voor IMKL datalevering is Rijksdriehoekmeting (RD), zie
[Referentiesystemen](#referentiesystemen).

**3D geometrie.**

IMKL voorziet in een verplicht gebruik van 2D geometrieën. Middels de diepte-
informatie kan de positie in het verticale vlak worden uitgewisseld. Om ook het
opnemen van volledige 3D liggingsgegevens mogelijk te maken is er een optioneel
en additioneel 3D model toegevoegd. De 3D liggingsgegevens van kabels en
leidingen zijn bijvoorbeeld relevant bij gestuurde boringen. Bij een gestuurde
boring is de derde dimensie (z-coördinaat) nodig om de boring te sturen, om het
uittredepunt goed te benaderen en om botsingen met andere infrastructuur te
voorkomen. Daardoor is na de boring de 3D ligging van de boring in 3D bekend.
Ook voor andere kabels en leidingen die tegenwoordig worden aangelegd, is steeds
vaker de 3D ligging bekend. Het niet accommoderen van deze 3D informatie in IMKL
zou in feite betekenen dat relevante informatie wordt weggegooid.

Voor veel situaties is 2D data echter (nog) voldoende. Bovendien is voor veel
kabels en leidingen de 3D (diepte) ligging niet bekend en door “zweven” van
sommige typen kabels en leidingen is de 3D (maar ook 2D ligging) niet altijd
absoluut. 3D geometrie kan daarbij een verkeerde indruk geven van de precisie.

In IMKL is de mogelijkheid opgenomen om objecten in 3 dimensies (3D) te
modelleren. Deze mogelijkheid is optioneel en is naast, niet in plaats van, 2D
aanwezig. Dat betekent dat de basis uitgaat van een (volledige) 2D data set.
Daarnaast kan, in dezelfde data set, 3D geometrie voor een of meerdere van de
objecten aanwezig zijn.

<div class="imageinfo ">
            <figure><img src="data/Images/EAID_845D41C0_FA2E_4667_B6B3_3B744D16F0D5.png" usemap="#imagemap-EAID_845D41C0_FA2E_4667_B6B3_3B744D16F0D5" alt="Diagram: 05.IMKL-Geometrie2 - detail"><figcaption>Alle netelementen kunnen naast de verplichte punten en centerlijnen
optioneel een extra geometrie hebben van het type 2D, 2,5D of 3D</figcaption>
            </figure><map name="imagemap-EAID_845D41C0_FA2E_4667_B6B3_3B744D16F0D5"><area shape="rect" alt="ContainerLeidingelement" coords="301,365,584,545" href="#global_class_IMKLBasis_ContainerLeidingelement"><area shape="rect" alt="Leidingelement" coords="195,560,478,723" href="#global_class_IMKLBasis_Leidingelement"><area shape="rect" alt="KabelEnLeidingContainer" coords="109,735,392,880" href="#global_class_IMKLBasis_KabelEnLeidingContainer"><area shape="rect" alt="KabelOfLeiding" coords="37,890,320,1035" href="#global_class_IMKLBasis_KabelOfLeiding"><area shape="rect" alt="Utiliteitsnet" coords="503,14,843,299" href="#global_class_IMKLBasis_Utiliteitsnet"><area shape="rect" alt="ExtraGeometrie" coords="38,14,325,299" href="#global_class_IMKLBasis_ExtraGeometrie"></map>
         </div>

<!--![](docs/media/5.IMKL-Geometrie2.png)-->

<!-- Figuur 5.5: Alle netelementen kunnen naast de verplichte punten en centerlijnen
optioneel een extra geometrie hebben van het type 2D, 2,5D of 3D. -->
<!--
<figure id="afb_IMKL-Geometrie2">
    <img src="docs/media/5.IMKL-Geometrie2.png" alt="Afbeelding Geometrie 2">
    <figcaption>Alle netelementen kunnen naast de verplichte punten en centerlijnen
optioneel een extra geometrie hebben van het type 2D, 2,5D of 3D.</figcaption>
</figure>
-->
KabelOfLeiding, KabelEnLeidingContainer, Leidingelement en
ContainerLeidingelement bieden ieder de mogelijkheid voor het opnemen van 3D
geometrie in twee verschillende ‘Levels of Detail’ (LOD). Allereerst kunnen 2.5D
punten, vlakken en lijnen worden opgenomen. Dit kan beschouwd worden als Level
of Detail 0 (LOD0) en is bedoeld voor het toevoegen van de z coördinaat. Elk
IMKL vlak, lijn- of puntobject krijgt voor elk coördinatenpaar een z waarde. Om
de ligging in 3D te beschrijven krijgt de lijn extra coördinatenparen ten
opzichte van de 2D representatie. De objecten kunnen dan in een Digitaal Terrein
Model (3D terreinmodel) worden geïntegreerd en op de juiste hoogte onder of
boven maaiveldniveau worden gerepresenteerd.

Daarnaast is het mogelijk om volledige 3D geometrie op te nemen. Dit is te
beschouwen als Level of Detail 1 (LOD1) en maakt het mogelijk om IMKL objecten
als volledige 3D objecten (volumes) te representeren. Zie [Figuur Leidingobject in 2.5D en 3D](#afb_Figuur5.6) voor
voorbeelden van een IMKL object op verschillende levels of detail.

Voor 3D IMKL wordt het ruimtelijk Referentie systeem EPSG:7415 gehanteerd. Dit
is een samengesteld referentiesysteem met RD voor de XY-dimensie (EPSG:28992) en
NAP voor de Z dimensie (EPSG:5709). Zie ook paragraaf [Ruimtelijk referentiesysteem](#ruimtelijk-referentiesysteem).

<!-- ![](docs/media/Figuur5.6.png) -->

<!-- Figuur 5.6: Leidingobject in 2.5D en 3D -->

<figure id="afb_Figuur5.6">
    <img src="docs/media/Figuur5.6.png" alt="Afbeelding Leidingobject in 3D">
    <figcaption>Leidingobject in 2.5D en 3D</figcaption>
</figure>

### Diepte

Diepte bevat informatie over de dieptelegging van netwerkelementen. Het is een
uitvoerige beschrijving die diepte tov het lokale maaiveld beschrijft of dieptes
tov NAP. Beide hebben een apart objecttype, respectievelijk DiepteTovMaaiveld en
DiepteNAP. Het cijfer dat bij de diepte hoort wordt opgenomen bij het attribuut
dieptepeil. Het betreft de afstand vanaf de referentie tot aan de *bovenkant*
van een object KabelOfleiding, KabelEnLeidingContainer, Leidingelement of
Containerleidinglelement. Het attribuut diepteAangrijpingspunt geeft het
aangrijpingspunt van het element weer dat geldt als punt van meting. Standaard
wordt daar bovenkant ingevuld maar het kan zinvol zijn om bij een buis
(riolering) *additioneel* ook de binnenonderkant buis (BOB) als meetpunt op te
nemen (zie ook Gegevenswoordenboek Stedelijk Water:
[http://data.gwsw.nl/totaal/binnenonderkantbuis](http://data.gwsw.nl/totaal/binnenonderkantbuis/). Het datatype van dieptepeil
is ‘Measure’ waarbij de meeteenheid apart wordt gespecificeerd. Voor WIBON wordt
er altijd meters gebruikt met maximaal 2 decimalen.

Er is informatie over de nauwkeurigheid waarmee de diepte is opgenomen. Dit is
de nauwkeurigheid van de meting op de dag van de legging of het moment van een
revisie van deze informatie. Daarvoor zijn 4 nauwkeurigheidsklassen opgenomen.
De nauwkeurigheid moet minstens +- 1 meter zijn. Bij het utiliteitsnet is een
attribuut standaardDieptelegging opgenomen, die is daarmee expliciet gemaakt.

Eén leiding kan meerdere dieptegegevens langs het traject van de leiding hebben.
Omdat hierdoor de diepte informatie en het object leiding niet meer 1 op 1 aan
elkaar gekoppeld zijn kan via het attribuut ligging de locatie van het
dieptegegeven worden aangegeven. De diepte geldt op die locatie. Een object
Diepte heeft ook de attributen van het object Label. Hiermee kunnen
verschillende dieptes middels annotatie aan één leiding worden gekoppeld.

Indien de dieptegegevens niet aan een netelement te koppelen zijn omdat die
koppeling bij de bronregistratie niet aanwezig is, zijn de dieptegegevens direct
aan het utiliteitsnet gekoppeld.

<div class="imageinfo ">
            <figure><img src="data/Images/EAID_2C1BCF04_8F33_4a4d_BE55_E985AF30AEA8.png" usemap="#imagemap-EAID_2C1BCF04_8F33_4a4d_BE55_E985AF30AEA8" alt="Diagram: 07.IMKL-Diepte - detail"><figcaption>Dieptegegevens zijn gemodelleerd als aparte objecten waarin diepte
ten opzicht van maaiveld en of NAP is opgenomen. Standaard dieptelegging wordt
opgenomen bij het Utiliteitsnet, afwijking daarvan bij de netelementen.</figcaption>
            </figure><map name="imagemap-EAID_2C1BCF04_8F33_4a4d_BE55_E985AF30AEA8"><area shape="rect" alt="KabelEnLeidingContainer" coords="752,14,1084,146" href="#global_class_IMKLBasis_KabelEnLeidingContainer"><area shape="rect" alt="ContainerLeidingelement" coords="1118,14,1450,194" href="#global_class_IMKLBasis_ContainerLeidingelement"><area shape="rect" alt="Leidingelement" coords="383,14,715,176" href="#global_class_IMKLBasis_Leidingelement"><area shape="rect" alt="KabelOfLeiding" coords="14,14,346,159" href="#global_class_IMKLBasis_KabelOfLeiding"><area shape="rect" alt="Utiliteitsnet" coords="1134,347,1440,633" href="#global_class_IMKLBasis_Utiliteitsnet"><area shape="rect" alt="DiepteTovMaaiveld" coords="674,812,892,957" href="#global_class_IMKLBasis_DiepteTovMaaiveld"><area shape="rect" alt="DiepteNAP" coords="332,812,623,987" href="#global_class_IMKLBasis_DiepteNAP"><area shape="rect" alt="Diepte" coords="447,320,846,641" href="#global_class_IMKLBasis_Diepte"><area shape="rect" alt="DiepteAangrijpingspuntValue" coords="161,499,383,586" href="#global_class_IMKLBasis_DiepteAangrijpingspuntValue"><area shape="rect" alt="NauwkeurigheidDiepteValue" coords="161,383,362,458" href="#global_class_IMKLBasis_NauwkeurigheidDiepteValue"></map>
         </div>

<!-- ![](docs/media/7.IMKL-Diepte.png) -->

<!-- Figuur 5.7: Dieptegegevens zijn gemodelleerd als aparte objecten waarin diepte
ten opzicht van maaiveld en of NAP is opgenomen. Standaard dieptelegging wordt
opgenomen bij het Utiliteitsnet, afwijking daarvan bij de netelementen. -->
<!--
<figure id="afb_7.IMKL-Diepte.png">
    <img src="docs/media/7.IMKL-Diepte.png" alt="Afbeelding Diepte">
    <figcaption>Dieptegegevens zijn gemodelleerd als aparte objecten waarin diepte
ten opzicht van maaiveld en of NAP is opgenomen. Standaard dieptelegging wordt
opgenomen bij het Utiliteitsnet, afwijking daarvan bij de netelementen.</figcaption>
</figure>
-->
### Utiliteitsnet

Definitie: Een verzameling netwerkelementen die tot één type
nutsvoorzieningennet behoren.

Bron: INSPIRE

Een Utiliteitsnet (nutsvoorzieningnetwerk, utiliteitsnetwerk, netwerk of net) is
de IMKL versie van het INSPIRE UtilityNetwork. Een Utiliteitsnet bevat geen
eigen geometrie maar is de samenstelling van alle gerefereerde netwerkelementen.
Het associatie attribuut elements realiseert deze verwijzing. Deze elements
associatie wordt echter niet gebruikt omdat de inverse associatie inNetwork de
associatie al realiseert. Alle netwerkelementen van een Utiliteitsnet vallen
onder het thema dat bij het utiliteitsnet hoort en worden daar ook door
getypeerd. Dat wil zeggen dat bijvoorbeeld een kathodische bescherming voor een
waterleiding valt onder een utiliteitsnet met het thema laagspanning. Via
INSPIRE UtilityNetwork worden attributen voor netwerktype en verantwoordelijke
partijen gekoppeld. Utiliteitsnet bevat extra attributen voor thema en
standaardDieptelegging. Door de referentie vanuit de Belanghebbende is de
verantwoordelijke netbeheerder gekoppeld. Annotatie, maatvoering en mogelijk
extra detailinfo worden gekoppeld en gelden voor het hele net (of deel daarvan
in een bestand).

<div class="imageinfo ">
            <figure><img src="data/Images/EAID_AD9408D7_15CD_400d_A04D_1AA40AB6B129.png" usemap="#imagemap-EAID_AD9408D7_15CD_400d_A04D_1AA40AB6B129" alt="Diagram: 08.IMKL-Utiliteitsnet - detail"><figcaption>Utiliteitsnet is getypeerd naar thema en wordt voor WIBON
gerefereerd door een Belanghebbende. Utiliteitsnet is een verbijzondering van
INSPIRE UtilityNetwork.</figcaption>
            </figure><map name="imagemap-EAID_AD9408D7_15CD_400d_A04D_1AA40AB6B129"><area shape="rect" alt="BestandMediaTypeValue" coords="23,1268,254,1338" href="#global_class_IMKLBasis_BestandMediaTypeValue"><area shape="rect" alt="ExtraDetailInfoTypeValue" coords="23,1148,254,1218" href="#global_class_IMKLBasis_ExtraDetailInfoTypeValue"><area shape="rect" alt="MaatvoeringsTypeValue" coords="944,29,1175,98" href="#global_class_IMKLBasis_MaatvoeringsTypeValue"><area shape="rect" alt="AnnotatieTypeValue" coords="694,29,925,98" href="#global_class_IMKLBasis_AnnotatieTypeValue"><area shape="rect" alt="NauwkeurigheidDiepteValue" coords="1011,1030,1242,1100" href="#global_class_IMKLBasis_NauwkeurigheidDiepteValue"><area shape="rect" alt="DiepteAangrijpingspuntValue" coords="1011,932,1242,1002" href="#global_class_IMKLBasis_DiepteAangrijpingspuntValue"><area shape="rect" alt="ExtraDetailinfo" coords="23,793,354,1115" href="#global_class_IMKLBasis_ExtraDetailinfo"><area shape="rect" alt="ExtraInformatie" coords="142,522,425,685" href="#global_class_IMKLBasis_ExtraInformatie"><area shape="rect" alt="Annotatie" coords="368,14,651,299" href="#global_class_IMKLBasis_Annotatie"><area shape="rect" alt="Maatvoering" coords="14,14,331,299" href="#global_class_IMKLBasis_Maatvoering"><area shape="rect" alt="Organisatie" coords="1848,161,2076,431" href="#global_class_LeveringGebiedsinformatie_Organisatie"><area shape="rect" alt="Beheerder" coords="1532,250,1781,488" href="#global_class_LeveringGebiedsinformatie_Beheerder"><area shape="rect" alt="Belanghebbende" coords="991,145,1365,448" href="#global_class_LeveringGebiedsinformatie_Belanghebbende"><area shape="rect" alt="Utiliteitsnet" coords="601,364,907,631" href="#global_class_IMKLBasis_Utiliteitsnet"><area shape="rect" alt="DiepteTovMaaiveld" coords="772,1235,991,1380" href="#global_class_IMKLBasis_DiepteTovMaaiveld"><area shape="rect" alt="DiepteNAP" coords="425,1234,716,1409" href="#global_class_IMKLBasis_DiepteNAP"><area shape="rect" alt="Diepte" coords="545,825,944,1147" href="#global_class_IMKLBasis_Diepte"><area shape="rect" alt="Thema" coords="1011,841,1242,910" href="#global_class_IMKLBasis_Thema"></map>
         </div>

<!-- ![](docs/media/8.IMKL-Utiliteitsnet.png) -->

<!-- Figuur 5.8: Utiliteitsnet is getypeerd naar thema en wordt voor WIBON
gerefereerd door een Belanghebbende. Utiliteitsnet is een verbijzondering van
INSPIRE UtilityNetwork. -->
<!--
<figure id="afb_8.IMKL-Utiliteitsnet">
    <img src="docs/media/8.IMKL-Utiliteitsnet.png" alt="Afbeelding Utiliteitsnet">
    <figcaption>Utiliteitsnet is getypeerd naar thema en wordt voor WIBON
gerefereerd door een Belanghebbende. Utiliteitsnet is een verbijzondering van
INSPIRE UtilityNetwork.</figcaption>
</figure>
-->
In INSPIRE is er voor UtilityNetwork met het attribuut utilityFacilityReference
een referentie mogelijk naar een ActivityComplex. Hiermee kan gerefereerd worden
aan grote utiliteitsnetonderdelen zoals bijvoorbeeld een energiecentrale een
waterzuiveringscentrale, een overslagstation. Het huidige IMKL ondersteunt
echter niet de opname van het objecttype ActivityComplex en evenmin het
attribuut utilityFacilityReference.

### KabelOfLeiding

Definitie: Leidingen, buizen of kabels bestemd voor voortgeleiding van energie,
materie of data.

Bron: IMKL

KabelOfLeiding is de verzamelklasse voor alle kabel en leiding typen per type
net (per ‘thema’). In het INSPIRE Utility networks model zijn de kabel- en
leidingtypen apart benoemd, de telecomkabel, de elektriciteitskabel enz.

Detailverwijzingen, annotatie en maatvoering zijn gekoppeld via het
associatie-attribuut heeftExtraInformatie. Informatie over een mogelijke
voorzorgsmaatregel bij graven is via verwijzing naar een object
AanduidingEisVoorzorgsmaatregel. Deze kan voor een geheel of een deel van kabel
of leiding gelden. De tekst van de voorzorgsmaatregel is bij het object
AanduidingEisVoorzorgsmaatregel opgenomen.

KabelOfLeiding zijn individuele kabels en of leidingen. Ze zijn dus niet een
verzameling. Voor dat laatste wordt de klasse KabelEnLeidingContainer gebruikt
en specifiek het object Kabelbed.

De nauwkeurigheid van de liggingsgegevens in het horizontale vlak wordt
aangegeven met een nauwkeurigheidXYvalue. Dit kan in een drietal klassen: tot 30
cm, tot 50 cm, tot 100 cm. In IMKL is de minimale nauwkeurigheid +- 1 meter.

Kabel of leidingen hebben verplicht een lijngeometrie. Optioneel is er via het
associatie-attribuut extraGeometrie een buitenbegrenzing of contour van het
object op te nemen. De netbeheerder bepaalt zelf wanneer dat functioneel is.

<div class="imageinfo ">
            <figure><img src="data/Images/EAID_B4FE45E4_C56A_4f70_8CB0_A607AB5D04F9.png" usemap="#imagemap-EAID_B4FE45E4_C56A_4f70_8CB0_A607AB5D04F9" alt="Diagram: 09.IMKL-KabelOfLeiding - detail"><figcaption>KabelOfLeiding bevat de gemeenschappelijke informatie voor kabels en
leidingen.</figcaption>
            </figure><map name="imagemap-EAID_B4FE45E4_C56A_4f70_8CB0_A607AB5D04F9"><area shape="rect" alt="MaatvoeringsTypeValue" coords="1363,20,1587,79" href="#global_class_IMKLBasis_MaatvoeringsTypeValue"><area shape="rect" alt="BestandMediaTypeValue" coords="14,126,191,191" href="#global_class_IMKLBasis_BestandMediaTypeValue"><area shape="rect" alt="KleurKabelOfLeidingValue" coords="944,633,1175,700" href="#global_class_IMKLBasis_KleurKabelOfLeidingValue"><area shape="rect" alt="OverigSpecifiek" coords="575,1242,801,1382" href="#global_class_IMKLBasis_OverigSpecifiek"><area shape="rect" alt="ExtraGeometrie" coords="221,372,466,657" href="#global_class_IMKLBasis_ExtraGeometrie"><area shape="rect" alt="Overig" coords="547,935,765,1097" href="#global_class_IMKLBasis_Overig"><area shape="rect" alt="BuisSpecifiek" coords="1013,1242,1404,1346" href="#global_class_IMKLBasis_BuisSpecifiek"><area shape="rect" alt="ExtraInformatie" coords="627,191,854,336" href="#global_class_IMKLBasis_ExtraInformatie"><area shape="rect" alt="Maatvoering" coords="1363,92,1688,355" href="#global_class_IMKLBasis_Maatvoering"><area shape="rect" alt="AanduidingEisVoorzorgsmaatregel" coords="1363,400,1737,727" href="#global_class_IMKLBasis_AanduidingEisVoorzorgsmaatregel"><area shape="rect" alt="Mantelbuis" coords="1876,935,2121,1238" href="#global_class_IMKLBasis_Mantelbuis"><area shape="rect" alt="Telecommunicatiekabel" coords="303,935,522,1080" href="#global_class_IMKLBasis_Telecommunicatiekabel"><area shape="rect" alt="Elektriciteitskabel" coords="57,935,276,1080" href="#global_class_IMKLBasis_Elektriciteitskabel"><area shape="rect" alt="KabelSpecifiek" coords="190,1242,421,1346" href="#global_class_IMKLBasis_KabelSpecifiek"><area shape="rect" alt="ThermischePijpleiding" coords="1610,935,1856,1097" href="#global_class_IMKLBasis_ThermischePijpleiding"><area shape="rect" alt="Waterleiding" coords="1332,935,1578,1097" href="#global_class_IMKLBasis_Waterleiding"><area shape="rect" alt="Rioolleiding" coords="1063,935,1309,1097" href="#global_class_IMKLBasis_Rioolleiding"><area shape="rect" alt="OlieGasChemicalienPijpleiding" coords="789,935,1035,1097" href="#global_class_IMKLBasis_OlieGasChemicalienPijpleiding"><area shape="rect" alt="Annotatie" coords="998,14,1323,277" href="#global_class_IMKLBasis_Annotatie"><area shape="rect" alt="ExtraDetailinfo" coords="221,14,547,336" href="#global_class_IMKLBasis_ExtraDetailinfo"><area shape="rect" alt="KabelOfLeiding" coords="574,439,906,689" href="#global_class_IMKLBasis_KabelOfLeiding"><area shape="rect" alt="ExtraDetailInfoTypeValue" coords="14,14,191,79" href="#global_class_IMKLBasis_ExtraDetailInfoTypeValue"><area shape="rect" alt="NauwkeurigheidXYvalue" coords="943,537,1174,604" href="#global_class_IMKLBasis_NauwkeurigheidXYvalue"></map>
         </div>

<!-- ![](docs/media/9.IMKL-KabelOfLeiding.png) -->

<!-- Figuur 5.9: KabelOfLeiding bevat de gemeenschappelijke informatie voor kabels en
leidingen. -->
<!--
<figure id="afb_9.IMKL-KabelOfLeiding">
    <img src="docs/media/9.IMKL-KabelOfLeiding.png" alt="Afbeelding KabelOfLeiding">
    <figcaption>KabelOfLeiding bevat de gemeenschappelijke informatie voor kabels en
leidingen.</figcaption>
</figure>
-->
### Leidingelement

Definitie: Een object dat bij één of meerdere leidingen behoort en als node in
het netwerkmodel is opgenomen.

Bron: IMKL

Toelichting: Bijvoorbeeld objecten zoals een schakelkast, verdeelkast, kranen,
afsluiters, versterkers, kabelmof, rioolput, (druk)rioolgemaal, kathodische
bescherming, boorput, etc.

Een leidingelement kan zowel betrekking hebben op ondergrondse als op
bovengrondse delen van het net.

Leidingelement is de verzamelklasse voor alle typen leidingelementen. De typen
zijn niet als apart objecttype opgenomen maar als verzamelklasse Appurtenance.
In INSPIRE zijn de Appurtenances met een appurtenanceType attribuut verder
getypeerd. Deze typering kan nog verder uitgebreid worden. In [Bijlage 1 IMKL waardelijsten](#bijlage-1-imkl-waardelijsten) zijn de waarden voor AppurtenanceTypeValue opgenomen.

<div class="imageinfo ">
            <figure><img src="data/Images/EAID_C2206E97_7B48_4631_8F1F_5C7B423D9E5E.png" usemap="#imagemap-EAID_C2206E97_7B48_4631_8F1F_5C7B423D9E5E" alt="Diagram: 10.IMKL-Leidingelement - detail"><figcaption>Leidingelement bevat de gemeenschappelijke eigenschappen van alle
typen leidingelementen.</figcaption>
            </figure><map name="imagemap-EAID_C2206E97_7B48_4631_8F1F_5C7B423D9E5E"><area shape="rect" alt="AnnotatieTypeValue" coords="759,74,962,135" href="#global_class_IMKLBasis_AnnotatieTypeValue"><area shape="rect" alt="BestandMediaTypeValue" coords="14,118,191,186" href="#global_class_IMKLBasis_BestandMediaTypeValue"><area shape="rect" alt="Appurtenance" coords="626,778,845,974" href="#global_class_IMKLBasis_Appurtenance"><area shape="rect" alt="Leidingelement" coords="569,428,901,713" href="#global_class_IMKLBasis_Leidingelement"><area shape="rect" alt="ExtraGeometrie" coords="209,372,454,657" href="#global_class_IMKLBasis_ExtraGeometrie"><area shape="rect" alt="ExtraInformatie" coords="610,185,836,329" href="#global_class_IMKLBasis_ExtraInformatie"><area shape="rect" alt="Maatvoering" coords="1350,92,1676,355" href="#global_class_IMKLBasis_Maatvoering"><area shape="rect" alt="AanduidingEisVoorzorgsmaatregel" coords="1350,400,1725,727" href="#global_class_IMKLBasis_AanduidingEisVoorzorgsmaatregel"><area shape="rect" alt="Annotatie" coords="985,14,1311,277" href="#global_class_IMKLBasis_Annotatie"><area shape="rect" alt="ExtraDetailinfo" coords="209,14,534,336" href="#global_class_IMKLBasis_ExtraDetailinfo"><area shape="rect" alt="NauwkeurigheidXYvalue" coords="933,428,1111,503" href="#global_class_IMKLBasis_NauwkeurigheidXYvalue"><area shape="rect" alt="ExtraDetailInfoTypeValue" coords="14,23,191,92" href="#global_class_IMKLBasis_ExtraDetailInfoTypeValue"></map>
         </div>

<!-- ![](docs/media/10.IMKL-Leidingelement.jpg) -->

<!-- Figuur 5.10: Leidingelement bevat de gemeenschappelijke eigenschappen van alle
typen leidingelementen. -->
<!--
<figure id="afb_10.IMKL-Leidingelement">
    <img src="docs/media/10.IMKL-Leidingelement.jpg" alt="Afbeelding Leidingelement">
    <figcaption>Leidingelement bevat de gemeenschappelijke eigenschappen van alle
typen leidingelementen.</figcaption>
</figure>
-->
De geometrie van een Leidingelement is verplicht altijd een punt. Optioneel is
er via het associatie-attribuut extraGeometrie een buitenbegrenzing of contour
van het object op te nemen. De netbeheerder bepaalt zelf wanneer dat functioneel
is. Leidingen die aan een Leidingelement verbonden zijn hoeven niet tot aan de
puntrepresentatie door te lopen. Ze kunnen stoppen bij de buitengrens van het
element (ook als de contour niet is opgenomen), dat doen ze in werkelijkheid
immers ook. Met de Arc/Node topologie kan wel opgenomen worden dat de leiding
bij het leidingelement hoort.

Informatie over een eventuele eis voorzorgsmaatregel is middels een associatie
vanuit het object AanduidingEisVoorzorgsmaatregel gekoppeld.

De hoogte van een leidingelement is met het attribuut hoogte op te nemen. De
hoogte betreft de lengte van het hele leidingelement in verticale richting
ongeacht of er een deel zich onder of boven het maaiveld bevindt. Het datatype is
‘Length’ waarbij de meeteenheid apart wordt gespecificeerd. Voor WIBON wordt er
altijd meters gebruikt met maximaal 2 decimalen. Een leidingelement kan ook
opgenomen zijn in de grootschalige topografie. Indien dat het geval is kan het
overeenkomstige BGT_ID worden opgenomen.

**Extra toelichting: aansluiting, huisaansluiting, profielschets.**

Aansluitingen vormen de overgang tussen het net van de netbeheerder en de
afnemers. De aansluiting en huisaansluiting kan opgenomen worden als
rasterbestand of als specifieke kabel of leidingelementen. Indien de aansluiting
als schets wordt uitgewisseld is deze gecodeerd conform ExtraDetailInfo. Voor de
schets is er een verschil gemaakt tussen een aansluiting en specifiek
huisaansluiting. Een huisaansluiting is de verbinding met een huisaansluitpunt.
Een aansluiting is een verbinding met andere dan huisaansluitpunten. Een schets
van een huisaansluiting heeft verplicht een BAG adres. Voor een schets van een
aansluiting geldt die verplichting niet. Beide hebben verplicht een locatie
middels het attribuut ligging. Voor de huisaansluiting is dit de coördinaat van
het VBO (verblijfsobject) uit de BAG; voor de aansluiting een apart toegevoegde
geometrie van het type punt, lijn of vlak.

Het type profielschets wordt gebruikt indien er een dwars- en of lengteprofiel
van een kunstwerk of gestuurde boring wordt meegeleverd. Dit object heeft
optioneel een adres en verplicht een ligging middels een punt, lijn of vlak.

Het type overig wordt gebruikt voor alle andere detailschetsen. Een voorbeeld
daarvan is een projecttekening van geplande netelementen.

### KabelEnLeidingContainer

Definitie: Abstract data object dat de gemeenschappelijke attributen en
associaties bevat voor alle kabel- en leidingcontainer objecten.

Bron: IMKL

Gerelateerde definities:

Kabelbed: Ruimtebeslag dat door een gemeenschappelijk tracé van één of meer
kabels, buizen, HDPE- en/of mantelbuizen – die toebehoren aan één netbeheerder -
wordt gevormd.

Toelichting: Synoniem voor kabelbed is geul. Losse kabels of buizen die bij
elkaar in een kabelbed liggen. Informatie is opgenomen op het niveau van de set
van kabels of buizen.

Mantelbuis: Beschermingsbuis.

Toelichting: Met het object Mantelbuis wordt bedoeld een buis voor bescherming
van kabels, buizen en HDPE buizen. Mantelbuizen kunnen bij meerdere thema’s
geregistreerd staan. Ze moeten bij minstens één thema weergegeven worden maar
het mag bij meerdere. Indien een mantelbuis leeg is kan dit bij de toelichting
vermeld worden.

 <div class="imageinfo ">
            <figure><img src="data/Images/EAID_0BF000D9_CD62_4a26_9A3B_7114CDE9995C.png" usemap="#imagemap-EAID_0BF000D9_CD62_4a26_9A3B_7114CDE9995C" alt="Diagram: 11.IMKL-KabelEnLeidingContainer - detail"><figcaption>KabelEnleidingContainer omvat kabelbedden en mantelbuizen.</figcaption>
            </figure><map name="imagemap-EAID_0BF000D9_CD62_4a26_9A3B_7114CDE9995C"><area shape="rect" alt="MaatvoeringsTypeValue" coords="1357,14,1558,74" href="#global_class_IMKLBasis_MaatvoeringsTypeValue"><area shape="rect" alt="BestandMediaTypeValue" coords="14,126,191,189" href="#global_class_IMKLBasis_BestandMediaTypeValue"><area shape="rect" alt="InfoKabelbedkabel" coords="107,872,389,1138" href="#global_class_IMKLBasis_InfoKabelbedkabel"><area shape="rect" alt="BuisSpecifiek" coords="1352,858,1693,962" href="#global_class_IMKLBasis_BuisSpecifiek"><area shape="rect" alt="Mantelbuis" coords="970,790,1215,1076" href="#global_class_IMKLBasis_Mantelbuis"><area shape="rect" alt="Kabelbed" coords="476,1026,902,1205" href="#global_class_IMKLBasis_Kabelbed"><area shape="rect" alt="Duct" coords="484,790,702,970" href="#global_class_IMKLBasis_Duct"><area shape="rect" alt="KabelEnLeidingContainer" coords="586,407,999,657" href="#global_class_IMKLBasis_KabelEnLeidingContainer"><area shape="rect" alt="ExtraGeometrie" coords="210,372,466,657" href="#global_class_IMKLBasis_ExtraGeometrie"><area shape="rect" alt="ExtraInformatie" coords="611,185,838,329" href="#global_class_IMKLBasis_ExtraInformatie"><area shape="rect" alt="Maatvoering" coords="1352,92,1677,355" href="#global_class_IMKLBasis_Maatvoering"><area shape="rect" alt="AanduidingEisVoorzorgsmaatregel" coords="1352,400,1726,727" href="#global_class_IMKLBasis_AanduidingEisVoorzorgsmaatregel"><area shape="rect" alt="Annotatie" coords="987,14,1312,277" href="#global_class_IMKLBasis_Annotatie"><area shape="rect" alt="ExtraDetailinfo" coords="210,14,536,336" href="#global_class_IMKLBasis_ExtraDetailinfo"><area shape="rect" alt="NauwkeurigheidXYvalue" coords="1013,485,1190,545" href="#global_class_IMKLBasis_NauwkeurigheidXYvalue"><area shape="rect" alt="ExtraDetailInfoTypeValue" coords="14,29,191,92" href="#global_class_IMKLBasis_ExtraDetailInfoTypeValue"></map>
         </div>

<!-- ![](docs/media/11.IMKL-KabelEnLeidingContainer.png) -->

<!-- Figuur 5.11: KabelEnleidingContainer omvat kabelbedden en mantelbuizen. -->
<!--
<figure id="afb_11.IMKL-KabelEnLeidingContainer">
    <img src="docs/media/11.IMKL-KabelEnLeidingContainer.png" alt="Afbeelding KabelEnLeidingContainer">
    <figcaption>KabelEnleidingContainer omvat kabelbedden en mantelbuizen.</figcaption>
</figure>
-->
KabelEnLeidingContainer is de verzamelklasse voor een aantal objecten waarin
kabels of leidingen gegroepeerd zijn. In de praktijk is dat een duct of een
kabelbed (is geul), of een mantelbuis. Een pipe is in INSPIRE een buis voor
transport van een product en ook een buis waarin zich weer buizen en kabels
kunnen bevinden. Indien er een container mee wordt bedoeld is alleen een object
mantelbuis van toepassing. Een mantelbuis is hierbij zowel een buis voor
protectie van andere elementen als wel voor groepering. Een
KabelEnLeidingContainer kan ook opgenomen zijn in de grootschalige topografie.
Indien dat het geval is kan het overeenkomstige BGT_ID worden opgenomen.

Indien er meerdere kabels in een kabelbed liggen wordt het aantal kabels
verplicht opgenomen.

Een duct is een object uit INSPIRE en wordt gedefinieerd als: Een behuizing die
ertoe dient om door middel van een omhullende constructie kabels en leidingen te
beschermen en geleiden. (Engelse def: A Duct (or Conduit, or Duct-bank, or
Wireway) is a linear object which belongs to the structural network. It is the
outermost casing. A Duct may contain Pipe(s), Cable(s) or other Duct(s).) Omdat
de definitie van een kabelbed daar niet helemaal invalt is Kabelbed apart
toegevoegd.

De geometrie van een KabelEnLeidingContainer is verplicht altijd een lijn.
Optioneel is er via het associatie-attribuut extraGeometrie een buitenbegrenzing
of contour van het object op te nemen.

Net als KabelOfLeiding is er ook een relatie met een mogelijke eis
voorzorgmaatregel.

### ContainerLeidingelement

Definitie: Abstract data object dat de gemeenschappelijke attributen en
associaties bevat voor alle containerleidingelement objecten.

Bron: IMKL

<div class="imageinfo ">
            <figure><img src="data/Images/EAID_5171BFB5_2026_4028_8059_76FF9A726DE7.png" usemap="#imagemap-EAID_5171BFB5_2026_4028_8059_76FF9A726DE7" alt="Diagram: 12.IMKL-ContainerLeidingElement - detail"><figcaption>ContainerLeidingelement een verzamelklasse voor meestal
topografische objecten die een ondersteunende functie in een netwerk hebben.</figcaption>
            </figure><map name="imagemap-EAID_5171BFB5_2026_4028_8059_76FF9A726DE7"><area shape="rect" alt="MaatvoeringsTypeValue" coords="1350,22,1572,82" href="#global_class_IMKLBasis_MaatvoeringsTypeValue"><area shape="rect" alt="BestandMediaTypeValue" coords="14,116,191,184" href="#global_class_IMKLBasis_BestandMediaTypeValue"><area shape="rect" alt="Toren" coords="282,815,426,959" href="#global_class_IMKLBasis_Toren"><area shape="rect" alt="TechnischGebouw" coords="1149,815,1294,959" href="#global_class_IMKLBasis_TechnischGebouw"><area shape="rect" alt="Mast" coords="496,815,641,959" href="#global_class_IMKLBasis_Mast"><area shape="rect" alt="Kast" coords="712,815,857,959" href="#global_class_IMKLBasis_Kast"><area shape="rect" alt="Mangat" coords="931,815,1076,959" href="#global_class_IMKLBasis_Mangat"><area shape="rect" alt="ContainerLeidingelement" coords="562,420,894,705" href="#global_class_IMKLBasis_ContainerLeidingelement"><area shape="rect" alt="ExtraGeometrie" coords="209,372,454,657" href="#global_class_IMKLBasis_ExtraGeometrie"><area shape="rect" alt="ExtraInformatie" coords="610,184,836,329" href="#global_class_IMKLBasis_ExtraInformatie"><area shape="rect" alt="Maatvoering" coords="1350,92,1676,355" href="#global_class_IMKLBasis_Maatvoering"><area shape="rect" alt="AanduidingEisVoorzorgsmaatregel" coords="1350,400,1725,727" href="#global_class_IMKLBasis_AanduidingEisVoorzorgsmaatregel"><area shape="rect" alt="Annotatie" coords="985,14,1311,277" href="#global_class_IMKLBasis_Annotatie"><area shape="rect" alt="ExtraDetailinfo" coords="209,14,534,336" href="#global_class_IMKLBasis_ExtraDetailinfo"><area shape="rect" alt="NauwkeurigheidXYvalue" coords="923,420,1100,488" href="#global_class_IMKLBasis_NauwkeurigheidXYvalue"><area shape="rect" alt="ExtraDetailInfoTypeValue" coords="14,23,191,92" href="#global_class_IMKLBasis_ExtraDetailInfoTypeValue"></map>
         </div>

<!-- ![](docs/media/12.IMKL-ContainerLeidingElement.png) -->

<!-- Figuur 5.12: ContainerLeidingelement een verzamelklasse voor meestal
topografische objecten die een ondersteunende functie in een netwerk hebben. -->
<!--
<figure id="afb_12.IMKL-ContainerLeidingElement">
    <img src="docs/media/12.IMKL-ContainerLeidingElement.png" alt="Afbeelding ContainerLeidinelement">
    <figcaption>ContainerLeidingelement een verzamelklasse voor meestal
topografische objecten die een ondersteunende functie in een netwerk hebben.</figcaption>
</figure>
-->
ContainerLeidingelement omvat objecten die verschillende leidingelementen
groeperen. Bijvoorbeeld een elektriciteitskast met verschillende schakelaars,
moffen. Of een mast met verschillende antennes. De schakelaars, moffen,
antennes, zijn onderdeel van het logische net. De ContainerLeidingelementen zijn
additioneel aan het logische net. ContainerLeidingelementen zijn in veel
gevallen ook opgenomen in de grootschalige topografie. Indien dat het geval is
kan het overeenkomstige BGT_ID worden opgenomen. De geometrie van een
ContainerLeidinelement is verplicht altijd een punt. Optioneel is er via het
associatie-attribuut extraGeometrie een buitenbegrenzing of contour van het
object op te nemen. De netbeheerder bepaalt zelf wanneer dat functioneel is.

Containerleidingelementen kunnen bij meerdere thema’s geregistreerd staan. Ze
moeten bij minstens één thema weergegeven worden maar het mag bij meerdere.

Net als bij individuele leidingelementen is er een mogelijkheid om een eis
voorzorgsmaatregel op te nemen.

### Relaties tussen KabelEnLeiding, Leidingelement en container objecten 

INSPIRE modelleert de relatie tussen kabels en de mantelbuis of kabelbed waar ze
in liggen. Van belang is dat in IMKL het kabelbed als aparte specialisatie van
duct is gemodelleerd. Mantelbuis als specialisatie van Pipe. De buizen en
leidingen zijn gemodelleerd op het niveau van de individuele leidingen. Voor
Telecom kan er gebruik gemaakt worden van het kabelbed om gegroepeerde kabels
uit te wisselen zonder de individuele kabelinformatie.

De relaties die aangegeven kunnen worden met de respectievelijke associatie
attributen zijn:

cables: mantelbuis verwijst naar de kabels die er in liggen;

pipes: mantelbuis verwijst naar buizen die er in liggen;

pipes: mantelbuis verwijst naar mantelbuizen die er in liggen;

cables: kabelbed verwijst naar de kabels die er in liggen;

pipes: kabelbed verwijst naar buizen die er in liggen;

pipes:kabelbed verwijst naar de mantelbuizen die er in liggen;

ducts: kabelbed verwijst naar kabelbedden die er in liggen.

Deze relaties worden door de individuele kabels en leidingen overerft.

Deze relaties zijn optioneel (want ze komen niet altijd voor) en voidable.

<div class="imageinfo ">
            <figure><img src="data/Images/EAID_65383E3E_AAC5_4abd_94BB_5614AA7777C2.png" usemap="#imagemap-EAID_65383E3E_AAC5_4abd_94BB_5614AA7777C2" alt="Diagram: 13.IMKL-RelatiesTussenCableDuctPipe - detail"><figcaption>Relaties tussen buis, kabel en duct. Bijvoorbeeld een kabelbed
verwijst optioneel naar de kabels die er in liggen; een mantelbuis kan verwijzen
naar de kabels die het bevat.</figcaption>
            </figure><map name="imagemap-EAID_65383E3E_AAC5_4abd_94BB_5614AA7777C2"><area shape="rect" alt="Mantelbuis" coords="14,287,258,590" href="#global_class_IMKLBasis_Mantelbuis"><area shape="rect" alt="Kabelbed" coords="868,511,1103,690" href="#global_class_IMKLBasis_Kabelbed"><area shape="rect" alt="Duct" coords="868,287,1087,467" href="#global_class_IMKLBasis_Duct"></map>
         </div>

<!-- ![](docs/media/13.IMKL-RelatiesTussenCableDuctPipe.png)
Figuur 5.13: Relaties tussen buis, kabel en duct. Bijvoorbeeld een kabelbed
verwijst optioneel naar de kabels die er in liggen; een mantelbuis kan verwijzen
naar de kabels die het bevat. -->
<!--
<figure id="afb_13.IMKL-RelatiesTussenCableDuctPipe">
    <img src="docs/media/13.IMKL-RelatiesTussenCableDuctPipe.png" alt="Afbeelding RelatiesTussenCableDuctPipe">
    <figcaption>Relaties tussen buis, kabel en duct. Bijvoorbeeld een kabelbed
verwijst optioneel naar de kabels die er in liggen; een mantelbuis kan verwijzen
naar de kabels die het bevat.</figcaption>
</figure>
-->
<!-- ![](docs/media/bec0a83557082b393b2fe6c5d822371f.jpg) -->



<!-- Figuur 5.14: Voorbeeld van een type mantelbuis met daarin weer een aantal
mantelbuizen (hdpe-buizen), waarvan één met een telecomkabel. Het model
maakt verwijzingen tussen mantelbuizen en kabels mogelijk. -->

<figure id="afb_mantelbuis">
    <img src="docs/media/bec0a83557082b393b2fe6c5d822371f.jpg" alt="Afbeelding Mantelbuis">
    <figcaption>Voorbeeld van een type mantelbuis met daarin weer een aantal
mantelbuizen (hdpe-buizen), waarvan één met een telecomkabel. Het model
maakt verwijzingen tussen mantelbuizen en kabels mogelijk.</figcaption>
</figure>



<!-- ![](docs/media/da0f5a202720bb7f2acd0abc0a6ae08e.png) -->

<!-- Figuur 5.15: Mantelbuizen worden samen in een kabelbed gelegd. Het model maakt
de verwijzing tussen kabelbed en de daarin liggende mantelbuizen of kabels en
leidingen mogelijk. -->

<figure id="afb_kabelbed">
    <img src="docs/media/da0f5a202720bb7f2acd0abc0a6ae08e.png" alt="Afbeelding Kabelbed">
    <figcaption>Kabelbed</figcaption>
</figure>

### Diagram per type kabel of leiding

De volgende paragrafen behandelen de specifieke typen kabel of leidingen. Het
bevat de informatie van vorige paragrafen maar dan bekeken van uit de concrete
objecten uit specifieke netten. De diagrammen zijn onderling erg vergelijkbaar.

### Elektriciteitskabel

Definitie: Een aansluiting of reeks aansluitingen van een nutsvoorzieningennet
voor het overbrengen van elektriciteit van de ene locatie naar een andere.

Bron: INSPIRE

De elektriciteitskabel overerft van INSPIRE operatingVoltage en nominalVoltage
en via UtilityLinkSet is de status, warningTypeen het distributietype opgenomen.
Het distributietype is daarbij geen verplichte WIBON informatie. WarningType is
een boven de kabel liggend waarschuwingsmechanisme voor een ondergronds
netelement. Het attribuut “operatingVoltage” beschrijft de gebruiks- of
bedrijfsspanning op de leiding. “nominalVoltage” beschrijft de nominale
systeemspanning op de plaats van levering. Voor de rest gelden de KabelEnleiding
attributen.

       
<div class="imageinfo ">
            <figure><img src="data/Images/EAID_52048BEC_35F2_4eb7_A984_ADB0FE706FC4.png" usemap="#imagemap-EAID_52048BEC_35F2_4eb7_A984_ADB0FE706FC4" alt="Diagram: 14.IMKL-Elektriciteitskabel - detail"><figcaption>Elektriciteitskabel</figcaption>
            </figure><map name="imagemap-EAID_52048BEC_35F2_4eb7_A984_ADB0FE706FC4"><area shape="rect" alt="NauwkeurigheidXYvalue" coords="491,570,708,631" href="#global_class_IMKLBasis_NauwkeurigheidXYvalue"><area shape="rect" alt="KabelSpecifiek" coords="596,696,802,799" href="#global_class_IMKLBasis_KabelSpecifiek"><area shape="rect" alt="Diepte" coords="868,365,1267,686" href="#global_class_IMKLBasis_Diepte"><area shape="rect" alt="AanduidingEisVoorzorgsmaatregel" coords="943,23,1267,350" href="#global_class_IMKLBasis_AanduidingEisVoorzorgsmaatregel"><area shape="rect" alt="ExtraGeometrie" coords="20,12,265,298" href="#global_class_IMKLBasis_ExtraGeometrie"><area shape="rect" alt="ExtraInformatie" coords="327,153,471,298" href="#global_class_IMKLBasis_ExtraInformatie"><area shape="rect" alt="Elektriciteitskabel" coords="212,686,430,831" href="#global_class_IMKLBasis_Elektriciteitskabel"><area shape="rect" alt="KabelOfLeiding" coords="77,380,452,630" href="#global_class_IMKLBasis_KabelOfLeiding"></map>
         </div>

<!-- ![](docs/media/14.IMKL-Elektriciteitskabel.png) -->
<!--
<figure id="afb_14.IMKL-Elektriciteitskabel">
    <img src="docs/media/14.IMKL-Elektriciteitskabel.png" alt="Afbeelding Elektriciteitskabel">
    <figcaption>Elektriciteitskabel</figcaption>
</figure>
-->
### Telecommunicatiekabel

Definitie: Een aansluiting of reeks aansluitingen van een nutsvoorzieningennet
voor het overbrengen van signaalinformatie van de ene locatie naar een andere.

Bron: INSPIRE

Van INSPIRE wordt een CableMaterialType toegevoegd en via UtilityLinkSet is de
status, warningType en het distributietype opgenomen. Het distributietype is
daarbij geen verplichte WIBON informatie. WarningType is een boven de kabel
liggend waarschuwingsmechanisme voor een ondergronds netelement. Voor de rest
gelden de KabelEnleiding attributen. In [Bijlage 1 IMKL waardelijsten](#bijlage-1-imkl-waardelijsten) staan de waarden voor de CableMaterialType.

<div class="imageinfo ">
            <figure><img src="data/Images/EAID_71B96BBB_A10E_4a2a_8C3D_3ECDB6A28B21.png" usemap="#imagemap-EAID_71B96BBB_A10E_4a2a_8C3D_3ECDB6A28B21" alt="Diagram: 15.IMKL-TelecommunicationsCable - detail"><figcaption>Telecommunicatiekabel</figcaption>
            </figure><map name="imagemap-EAID_71B96BBB_A10E_4a2a_8C3D_3ECDB6A28B21"><area shape="rect" alt="NauwkeurigheidXYvalue" coords="496,571,685,633" href="#global_class_IMKLBasis_NauwkeurigheidXYvalue"><area shape="rect" alt="Telecommunicatiekabel" coords="164,681,383,821" href="#global_class_IMKLBasis_Telecommunicatiekabel"><area shape="rect" alt="KabelSpecifiek" coords="582,698,789,802" href="#global_class_IMKLBasis_KabelSpecifiek"><area shape="rect" alt="Diepte" coords="868,348,1267,670" href="#global_class_IMKLBasis_Diepte"><area shape="rect" alt="AanduidingEisVoorzorgsmaatregel" coords="943,14,1267,340" href="#global_class_IMKLBasis_AanduidingEisVoorzorgsmaatregel"><area shape="rect" alt="ExtraGeometrie" coords="20,26,265,312" href="#global_class_IMKLBasis_ExtraGeometrie"><area shape="rect" alt="ExtraInformatie" coords="327,156,471,318" href="#global_class_IMKLBasis_ExtraInformatie"><area shape="rect" alt="KabelOfLeiding" coords="77,383,452,633" href="#global_class_IMKLBasis_KabelOfLeiding"></map>
         </div>

<!-- ![](docs/media/15.IMKL-TelecommunicationsCable.png) -->
<!--
<figure id="afb_15.IMKL-TelecommunicationsCable">
    <img src="docs/media/15.IMKL-TelecommunicationsCable.png" alt="Afbeelding IMKL-Telecommunicatiekabel">
    <figcaption>Telecommunicatiekabel</figcaption>
</figure>
-->
### Olie-gas-chemicalienpijpleiding

Definitie: Een pijpleiding voor het overbrengen van olie, gas of chemicaliën van
de ene locatie naar een andere.

Bron: INSPIRE

Uit INSPIRE wordt oilGasChemicalProductType toegevoegd en via UtilityLinkSet is de
status, warningType en het distributietype opgenomen. Het distributietype is
daarbij geen verplichte WIBON informatie. WarningType is een boven de kabel
liggend waarschuwingsmechanisme voor een ondergronds netelement. Voor de rest
gelden de KabelEnleiding attributen.

In [Bijlage 1 IMKL waardelijsten](#bijlage-1-imkl-waardelijsten) staan de mogelijke waarden voor de producttypen.

<div class="imageinfo ">
            <figure><img src="data/Images/EAID_1378B654_4826_439f_9A6C_2F814962F4E0.png" usemap="#imagemap-EAID_1378B654_4826_439f_9A6C_2F814962F4E0" alt="Diagram: 16.IMKL-Olie-gas-chemicaliënpijpleiding - detail"><figcaption>Olie-gas-chemicaliënpijpleiding</figcaption>
            </figure><map name="imagemap-EAID_1378B654_4826_439f_9A6C_2F814962F4E0"><area shape="rect" alt="NauwkeurigheidXYvalue" coords="491,575,686,635" href="#global_class_IMKLBasis_NauwkeurigheidXYvalue"><area shape="rect" alt="BuisSpecifiek" coords="476,704,817,808" href="#global_class_IMKLBasis_BuisSpecifiek"><area shape="rect" alt="OlieGasChemicalienPijpleiding" coords="146,690,392,835" href="#global_class_IMKLBasis_OlieGasChemicalienPijpleiding"><area shape="rect" alt="Diepte" coords="856,351,1255,672" href="#global_class_IMKLBasis_Diepte"><area shape="rect" alt="AanduidingEisVoorzorgsmaatregel" coords="931,14,1255,340" href="#global_class_IMKLBasis_AanduidingEisVoorzorgsmaatregel"><area shape="rect" alt="ExtraGeometrie" coords="14,34,258,320" href="#global_class_IMKLBasis_ExtraGeometrie"><area shape="rect" alt="ExtraInformatie" coords="314,159,459,321" href="#global_class_IMKLBasis_ExtraInformatie"><area shape="rect" alt="KabelOfLeiding" coords="64,385,440,635" href="#global_class_IMKLBasis_KabelOfLeiding"></map>
         </div>

<!-- ![](docs/media/16.IMKL-Olie-gas-chemicaliënpijpleiding.png) -->
<!--
<figure id="afb_16.IMKL-Olie-gas-chemicaliënpijpleiding">
    <img src="docs/media/16.IMKL-Olie-gas-chemicaliënpijpleiding.png" alt="Afbeelding Olie-gas-chemicaliënpijpleiding">
    <figcaption>Olie-gas-chemicaliënpijpleiding</figcaption>
</figure>
-->
### Rioolleiding

Definitie: Een rioleringsleiding voor het overbrengen van afvalwater
(rioolwater, hemelwater) van de ene locatie naar een andere.

Bron: INSPIRE (aangepast)

Van INSPIRE wordt SewerWaterType toegevoegd en via UtilityLinkSet is de status,
warningType en het distributietype opgenomen. Het distributietype is daarbij
geen verplichte WIBON informatie WarningType is een boven de kabel liggend
waarschuwingsmechanisme voor een ondergronds netelement. Voor de rest gelden de
KabelEnleiding attributen. In [Bijlage 1 IMKL waardelijsten](#bijlage-1-imkl-waardelijsten).

        
<div class="imageinfo ">
            <figure><img src="data/Images/EAID_F1DDDB14_DA3A_422d_AD6B_11D32EC2505A.png" usemap="#imagemap-EAID_F1DDDB14_DA3A_422d_AD6B_11D32EC2505A" alt="Diagram: 17.IMKL-Rioolleiding - detail"><figcaption>Rioolleiding</figcaption>
            </figure><map name="imagemap-EAID_F1DDDB14_DA3A_422d_AD6B_11D32EC2505A"><area shape="rect" alt="NauwkeurigheidXYvalue" coords="495,575,723,637" href="#global_class_IMKLBasis_NauwkeurigheidXYvalue"><area shape="rect" alt="Rioolleiding" coords="157,686,403,831" href="#global_class_IMKLBasis_Rioolleiding"><area shape="rect" alt="BuisSpecifiek" coords="495,693,836,797" href="#global_class_IMKLBasis_BuisSpecifiek"><area shape="rect" alt="Diepte" coords="866,350,1266,671" href="#global_class_IMKLBasis_Diepte"><area shape="rect" alt="AanduidingEisVoorzorgsmaatregel" coords="942,7,1266,333" href="#global_class_IMKLBasis_AanduidingEisVoorzorgsmaatregel"><area shape="rect" alt="ExtraGeometrie" coords="19,27,264,313" href="#global_class_IMKLBasis_ExtraGeometrie"><area shape="rect" alt="ExtraInformatie" coords="325,157,470,320" href="#global_class_IMKLBasis_ExtraInformatie"><area shape="rect" alt="KabelOfLeiding" coords="78,387,454,637" href="#global_class_IMKLBasis_KabelOfLeiding"></map>
         </div>

<!-- ![](docs/media/17.IMKL-Rioolleiding.png) -->
<!--
<figure id="afb_17.IMKL-Rioolleiding">
    <img src="docs/media/17.IMKL-Rioolleiding.png" alt="Afbeelding Rioolleiding">
    <figcaption>Rioolleiding</figcaption>
</figure>
-->
### Waterleiding

Definitie: Een waterleiding voor het overbrengen van (drink)water van de ene
locatie naar een andere.

Bron:INSPIRE (aangepast)

Van INSPIRE wordt waterType toegevoegd en via UtilityLinkSet is de status,
warningType en het distributietype opgenomen. Het distributietype is daarbij
geen verplichte WIBON informatie. WarningType is een boven de kabel liggend
waarschuwingsmechanisme voor een ondergronds netelement. Voor de rest gelden de
KabelEnleiding attributen.

In [Bijlage 1 IMKL waardelijsten](#bijlage-1-imkl-waardelijsten) staan de waarden voor waterType.


<div class="imageinfo ">
            <figure><img src="data/Images/EAID_1BB71A77_AAF4_49ec_A828_741FC3EBB9E7.png" usemap="#imagemap-EAID_1BB71A77_AAF4_49ec_A828_741FC3EBB9E7" alt="Diagram: 18.IMKL-Waterleiding - detail"><figcaption>Waterleiding</figcaption>
            </figure><map name="imagemap-EAID_1BB71A77_AAF4_49ec_A828_741FC3EBB9E7"><area shape="rect" alt="NauwkeurigheidXYvalue" coords="496,573,685,627" href="#global_class_IMKLBasis_NauwkeurigheidXYvalue"><area shape="rect" alt="Waterleiding" coords="116,685,362,825" href="#global_class_IMKLBasis_Waterleiding"><area shape="rect" alt="BuisSpecifiek" coords="470,696,812,799" href="#global_class_IMKLBasis_BuisSpecifiek"><area shape="rect" alt="Diepte" coords="861,344,1260,666" href="#global_class_IMKLBasis_Diepte"><area shape="rect" alt="AanduidingEisVoorzorgsmaatregel" coords="936,7,1260,333" href="#global_class_IMKLBasis_AanduidingEisVoorzorgsmaatregel"><area shape="rect" alt="ExtraGeometrie" coords="14,22,258,307" href="#global_class_IMKLBasis_ExtraGeometrie"><area shape="rect" alt="ExtraInformatie" coords="320,152,465,314" href="#global_class_IMKLBasis_ExtraInformatie"><area shape="rect" alt="KabelOfLeiding" coords="70,377,446,627" href="#global_class_IMKLBasis_KabelOfLeiding"></map>
         </div>

<!-- ![](docs/media/18.IMKL-Waterleiding.png) -->
<!--
<figure id="afb_18.IMKL-Waterleiding">
    <img src="docs/media/18.IMKL-Waterleiding.png" alt="Afbeelding Waterleiding">
    <figcaption>Waterleiding</figcaption>
</figure>
-->
### Thermische pijpleiding

Definitie: Een leiding voor het transporteren van warmte of koelte van de ene
locatie naar een andere.

Bron: INSPIRE

Van INSPIRE wordt thermalProductType toegevoegd en via UtilityLinkSet is de
status, warningType en het distributietype opgenomen. Het distributietype is
daarbij geen verplichte WIBON informatie. WarningType is een boven de kabel
liggend waarschuwingsmechanisme voor een ondergronds netelement. Voor de rest
gelden de KabelEnleiding attributen.

In [Bijlage 1 IMKL waardelijsten](#bijlage-1-imkl-waardelijsten) staan de waarden voor de producttypen.

<div class="imageinfo ">
            <figure><img src="data/Images/EAID_48FEFF57_7B2A_47cc_91EE_EA7058A93A3E.png" usemap="#imagemap-EAID_48FEFF57_7B2A_47cc_91EE_EA7058A93A3E" alt="Diagram: 19.IMKL-ThermischePijpleiding - detail"><figcaption>Thermische Pijpleiding</figcaption>
            </figure><map name="imagemap-EAID_48FEFF57_7B2A_47cc_91EE_EA7058A93A3E"><area shape="rect" alt="NauwkeurigheidXYvalue" coords="482,577,681,640" href="#global_class_IMKLBasis_NauwkeurigheidXYvalue"><area shape="rect" alt="ThermischePijpleiding" coords="154,708,400,849" href="#global_class_IMKLBasis_ThermischePijpleiding"><area shape="rect" alt="BuisSpecifiek" coords="551,659,892,763" href="#global_class_IMKLBasis_BuisSpecifiek"><area shape="rect" alt="Diepte" coords="868,357,1267,678" href="#global_class_IMKLBasis_Diepte"><area shape="rect" alt="AanduidingEisVoorzorgsmaatregel" coords="943,14,1267,340" href="#global_class_IMKLBasis_AanduidingEisVoorzorgsmaatregel"><area shape="rect" alt="ExtraGeometrie" coords="20,34,265,320" href="#global_class_IMKLBasis_ExtraGeometrie"><area shape="rect" alt="ExtraInformatie" coords="327,164,471,327" href="#global_class_IMKLBasis_ExtraInformatie"><area shape="rect" alt="KabelOfLeiding" coords="77,390,452,640" href="#global_class_IMKLBasis_KabelOfLeiding"></map>
         </div>

<!-- ![](docs/media/19.IMKL-ThermischePijpleiding.png) -->
<!--
<figure id="afb_19.IMKL-ThermischePijpleiding">
    <img src="docs/media/19.IMKL-ThermischePijpleiding.png" alt="Afbeelding ThermischePijpleiding">
    <figcaption>Thermische Pijpleiding</figcaption>
</figure>
-->

### Overig en Weesleiding

Definitie Overig: Een type kabel of leiding die niet onder de andere benoemde
typen valt.

Bijvoorbeeld een weesleiding maar ook leidingen voor voedingsmiddelen,
landbouwproducten vallen hieronder.

Bron: IMKL

In INSPIRE is er geen mogelijkheid om andere kabels of leidingen op te nemen dan
de benoemde typen. De klasse Overig wordt gebruikt indien de kabel of leiding
niet met een andere kan worden aangeduid of onbekend is. Dit geldt in veel
gevallen ook voor de weesleiding. Er is een klasse OverigSpecifiek gemaakt om de
INSPIRE attributen pipeDiameter, pressure en producttype ook voor Overig te
kunnen gebruiken.

 
<div class="imageinfo ">
            <figure><img src="data/Images/EAID_39CD6BF9_0D4C_43b2_80DE_FA371DC3671C.png" usemap="#imagemap-EAID_39CD6BF9_0D4C_43b2_80DE_FA371DC3671C" alt="Diagram: 19b.IMKL-Overig-Weesleiding - detail"><figcaption>Overig/Weesleiding</figcaption>
            /figure><map name="imagemap-EAID_39CD6BF9_0D4C_43b2_80DE_FA371DC3671C"><area shape="rect" alt="NauwkeurigheidXYvalue" coords="555,581,748,640" href="#global_class_IMKLBasis_NauwkeurigheidXYvalue"><area shape="rect" alt="KabelSpecifiek" coords="14,916,220,1020" href="#global_class_IMKLBasis_KabelSpecifiek"><area shape="rect" alt="OverigSpecifiek" coords="14,769,239,909" href="#global_class_IMKLBasis_OverigSpecifiek"><area shape="rect" alt="Overig" coords="455,746,674,909" href="#global_class_IMKLBasis_Overig"><area shape="rect" alt="BuisSpecifiek" coords="14,657,355,761" href="#global_class_IMKLBasis_BuisSpecifiek"><area shape="rect" alt="Diepte" coords="871,357,1270,678" href="#global_class_IMKLBasis_Diepte"><area shape="rect" alt="AanduidingEisVoorzorgsmaatregel" coords="946,14,1270,340" href="#global_class_IMKLBasis_AanduidingEisVoorzorgsmaatregel"><area shape="rect" alt="ExtraGeometrie" coords="23,34,268,320" href="#global_class_IMKLBasis_ExtraGeometrie"><area shape="rect" alt="ExtraInformatie" coords="329,164,474,327" href="#global_class_IMKLBasis_ExtraInformatie"><area shape="rect" alt="KabelOfLeiding" coords="79,390,503,640" href="#global_class_IMKLBasis_KabelOfLeiding"></map>
         </div>

<!-- ![](docs/media/19b.IMKL-Overig-Weesleiding.png) -->
<!--
<figure id="afb_19b.IMKL-Overig-Weesleiding">
    <img src="docs/media/19b.IMKL-Overig-Weesleiding.png" alt="Afbeelding Overig-Weesleiding">
    <figcaption>Overig/Weesleiding</figcaption>
</figure>
-->
### Leidingelementen per type net (thema)

De leidingelementen worden niet specifiek per type thema net als de kabels en
leidingen gedefinieerd. Leidingelementen hebben een algemene type lijst en een
lijst per type net (telecom, elektriciteit, riool, water, gas/olie). Deze
lijsten zijn uitbreidbaar. In [Bijlage 1 IMKL waardelijsten](#bijlage-1-imkl-waardelijsten) staan de waardelijsten met de waarden
voor type leidingelement per type kabelOfLeiding.

<div class="imageinfo ">
            <figure><img src="data/Images/EAID_68316DB9_764E_4b6f_B63E_8A8A5D44F3B2.png" usemap="#imagemap-EAID_68316DB9_764E_4b6f_B63E_8A8A5D44F3B2" alt="Diagram: 20.IMKL-Leidingelement-per-thema - detail"><figcaption>Leidingelement per thema</figcaption>
            </figure><map name="imagemap-EAID_68316DB9_764E_4b6f_B63E_8A8A5D44F3B2"><area shape="rect" alt="NauwkeurigheidXYvalue" coords="555,612,737,668" href="#global_class_IMKLBasis_NauwkeurigheidXYvalue"><area shape="rect" alt="Leidingelement" coords="172,383,504,668" href="#global_class_IMKLBasis_Leidingelement"><area shape="rect" alt="Appurtenance" coords="250,722,469,897" href="#global_class_IMKLBasis_Appurtenance"><area shape="rect" alt="Diepte" coords="861,350,1260,671" href="#global_class_IMKLBasis_Diepte"><area shape="rect" alt="AanduidingEisVoorzorgsmaatregel" coords="936,14,1260,340" href="#global_class_IMKLBasis_AanduidingEisVoorzorgsmaatregel"><area shape="rect" alt="ExtraGeometrie" coords="14,27,258,313" href="#global_class_IMKLBasis_ExtraGeometrie"><area shape="rect" alt="ExtraInformatie" coords="320,157,465,320" href="#global_class_IMKLBasis_ExtraInformatie"></map>
         </div>

<!-- ![](docs/media/20.IMKL-Leidingelement-per-thema.png) -->
<!--
<figure id="afb_20.IMKL-Leidingelement-per-thema.png">
    <img src="docs/media/20.IMKL-Leidingelement-per-thema.png" alt="Afbeelding Leidingelement-per-thema">
    <figcaption>Leidingelement per thema</figcaption>
</figure>
-->
### WIBON Uitleveren van gebiedsinformatie

Voor het faciliteren van de uitlevergegevens binnen de WIBON is er naast de
specifieke utiliteitsnet informatie nog een aantal extra gegevens nodig. In
onderstaand diagram is de relatie tussen de verschillende onderdelen van de uitleveringsgegevens
weergegeven.

<!--![](docs/media/wibonuitlevering.png)-->
<figure id="afb_wibonuitlevering">
    <img src="docs/media/wibonuitlevering.png" alt="Afbeelding uitlevering">
    <figcaption>De verschillende onderdelen in de WIBON Uitlevering</figcaption>
</figure>

WIBON Uitlevering: Het totaal aan informatie dat kan worden geleverd bij een
WIBON informatieaanvraag.

Leveringsinformatie: Administratieve gegevens van de uitlevering inclusief de
aanvraaggegevens met graaf-, informatie- en oriëntatiepolygoon.

Beheerdersinformatie: De belanghebbende beheerder, bijlagen inclusief ev brief
en contactgegevens.

Netinformatie: Informatie over het utiliteitsnet, onderdelen, details en extra
aanduidingen.

Om de informatie uit het middelste blok te genereren is er een
Belangenregistratie nodig. Hierin zijn de belangen van de netbeheerders
geregistreerd en is per netbeheerder per thema de beheerpolygoon inclusief
contactinformatie opgenomen.

Deze blokken zijn nader ingevuld in het UML diagram op de volgende pagina.

<div class="imageinfo ">
            <figure><img src="data/Images/EAID_B6363351_D2FC_4278_9335_F25A998CC626.png" usemap="#imagemap-EAID_B6363351_D2FC_4278_9335_F25A998CC626" alt="Diagram: 20a.IMKL-Levering-Gebiedsinformatie - detail"><figcaption>Model voor levering gebiedsinformatie</figcaption>
            </figure><map name="imagemap-EAID_B6363351_D2FC_4278_9335_F25A998CC626"><area shape="rect" alt="BestandMediaTypeValue" coords="1516,724,1691,783" href="#global_class_IMKLBasis_BestandMediaTypeValue"><area shape="rect" alt="MaximaleWerkdiepteValue" coords="1360,530,1544,589" href="#global_class_IMKLBasis_MaximaleWerkdiepteValue"><area shape="rect" alt="GraafmethodeValue" coords="1565,530,1749,589" href="#global_class_IMKLBasis_GraafmethodeValue"><area shape="rect" alt="SoortWerkzaamhedenValue" coords="1565,417,1749,476" href="#global_class_IMKLBasis_SoortWerkzaamhedenValue"><area shape="rect" alt="WerkzaamhedenInfo" coords="1706,227,2058,366" href="#global_class_LeveringGebiedsinformatie_WerkzaamhedenInfo"><area shape="rect" alt="EisVoorzorgsmaatregelBijlage" coords="1171,719,1492,987" href="#global_class_IMKLBasis_EisVoorzorgsmaatregelBijlage"><area shape="rect" alt="Achtergrondkaart" coords="115,405,437,526" href="#global_class_IMKLBasis_Achtergrondkaart"><area shape="rect" alt="Beheerder" coords="1721,984,1969,1222" href="#global_class_LeveringGebiedsinformatie_Beheerder"><area shape="rect" alt="Utiliteitsnet" coords="66,1386,339,1654" href="#global_class_IMKLBasis_Utiliteitsnet"><area shape="rect" alt="EigenTopografie" coords="1056,1061,1394,1311" href="#global_class_IMKLBasis_EigenTopografie"><area shape="rect" alt="Belanghebbende" coords="52,996,339,1300" href="#global_class_LeveringGebiedsinformatie_Belanghebbende"><area shape="rect" alt="Belang" coords="414,734,728,989" href="#global_class_LeveringGebiedsinformatie_Belang"><area shape="rect" alt="AanvraagSoortContact" coords="868,722,1117,879" href="#global_class_LeveringGebiedsinformatie_AanvraagSoortContact"><area shape="rect" alt="Adres" coords="1707,724,1997,953" href="#global_class_IMKLBasis_Adres"><area shape="rect" alt="Organisatie" coords="1768,372,1997,641" href="#global_class_LeveringGebiedsinformatie_Organisatie"><area shape="rect" alt="Contact" coords="1792,60,1997,200" href="#global_class_LeveringGebiedsinformatie_Contact"><area shape="rect" alt="Opdrachtgever" coords="1360,261,1561,383" href="#global_class_LeveringGebiedsinformatie_Opdrachtgever"><area shape="rect" alt="Aanvrager" coords="1343,94,1544,234" href="#global_class_LeveringGebiedsinformatie_Aanvrager"><area shape="rect" alt="Orientatiepolygoon" coords="1050,499,1218,642" href="#global_class_LeveringGebiedsinformatie_Orientatiepolygoon"><area shape="rect" alt="Informatiepolygoon" coords="1050,261,1333,476" href="#global_class_LeveringGebiedsinformatie_Informatiepolygoon"><area shape="rect" alt="Graafpolygoon" coords="1050,101,1218,245" href="#global_class_LeveringGebiedsinformatie_Graafpolygoon"><area shape="rect" alt="GebiedsinformatieAanvraag" coords="491,79,876,672" href="#global_class_LeveringGebiedsinformatie_GebiedsinformatieAanvraag"><area shape="rect" alt="GebiedsinformatieLevering" coords="34,79,301,347" href="#global_class_LeveringGebiedsinformatie_GebiedsinformatieLevering"><area shape="rect" alt="AanvraagSoortValue" coords="1360,414,1544,473" href="#global_class_IMKLBasis_AanvraagSoortValue"><area shape="rect" alt="AchtergrondkaartSoortValue" coords="230,548,429,620" href="#global_class_IMKLBasis_AchtergrondkaartSoortValue"><area shape="rect" alt="EigenTopografieStatusValue" coords="1415,1103,1614,1177" href="#global_class_IMKLBasis_EigenTopografieStatusValue"><area shape="rect" alt="Thema" coords="519,1430,750,1517" href="#global_class_IMKLBasis_Thema"></map>
         </div>
<!--
<figure id="20a.IMKL-Levering-Gebiedsinformatie">
    <img src="docs/media/20a.IMKL-Levering-Gebiedsinformatie.png" alt="Afbeelding Levering Gebiedsinformatie">
    <figcaption>Model voor levering gebiedsinformatie</figcaption>
</figure>
-->
<!-- [](docs/media/20a.IMKL-Levering-Gebiedsinformatie.png) -->

Toelichting bij het diagram.

Met verschillende kleur omlijningen is aangegeven hoe het objecttype zich
verhoudt tot verschil in aanlevering aan de centrale voorziening door centraal
of decentraal aangesloten netbeheerder of in de aan- of uitlevering

-   Rood omlijnd: gegevens die door de centrale voorziening worden gegenereerd.
    Komen alleen voor in uitlevering.

-   Groen omlijnd: gegevens die voor de centraal aangesloten netbeheerder door
    de voorziening wordt gegenereerd. Decentraal aangesloten netbeheerders
    moeten deze gegevens per melding aan de centrale voorziening leveren.

-   Op het niveau van attributen is met een constraint aangegeven indien er
    verschil is met betrekking tot aan- of uitlevering of decentraal of centraal
    aangesloten netbeheerder.

Het object GebiedsinformatieLevering verwijst naar de gegevens van de
GebiedsinformatieAanvraag die de aanvraaggegevens bevat en een graaf- en/of een
oriëntatiepolygoon. De informatiepolygoon is de weergave door een grondroerder
van het gebied, waarvoor gebiedsinformatie wordt aangevraagd. Bij de uitlevering
wordt die ook meegegeven inclusief de visualisatie van het gebied tussen de
graaf- en de informatiepolygoon. In [Bijlage D: Toelichting op informatiepolygoon](#bijlage-toelichting-op-informatiepolygoon) wordt dit gebied toegelicht.


De GebiedsinformatieLevering verwijst naar een object Belanghebbende waarin de
beheerdersinformatie is opgenomen. Bij de Gebiedsinformatielevering hoort
verplicht een verwijzing naar de BGT als achtergrondkaart. Dit kan in raster- of
in vectorformaat zijn

Een belanghebbende beheerder is een beheerder met een beheerpolygoon dat geheel
of gedeeltelijk ligt in de polygoon van de gebiedsinformatie aanvraag. Een
beheergebied hoort altijd groter te zijn dan het gebied waar de netbeheerder
informatie over kabels en leidingen wil leveren. Daarom hoeft een belanghebbende
beheerder niet altijd een betrokken beheerder te zijn. Bij de aanlevering naar
de centrale voorziening gelden andere condities voor de attributen dan voor de
uitlevering. Ook een beheerder veiligheidsgebied heeft een beheerpolygoon en kan
een belanghebbende beheerder zijn. Deze zal echter geen beheerdersinformatie
aanleveren en wordt niet opgenomen in de levering van gebiedsinformatie.

Het object Belanghebbende heeft 1 of meer geraakte belangen en de daarbij
horende contactgegevens (zie [Belangenregistratie](#belangenregistratie)). Tevens is er een verwijzing
vanuit de belanghebbende naar de eventuele bijlagen, inclusief bijlage
Eisvoorzorgsmaatregel. De bijlagen zijn daarmee direct gerelateerd aan de
belanghebbende en pas indirect aan het utiliteitsnet. Een belanghebbende kan een
belang hebben maar niet betrokken zijn.

Indien de belanghebbende wel betrokken is dan is er ook netinformatie
beschikbaar via een relatie naar één of meerdere utiliteitsnetten.

Het object Utiliteitsnet vormt de verbinding naar de locatie en typegegevens van
het utiliteitsnet met de netwerkelementen en gerelateerde informatie.

### Belangenregistratie
De Belangenregistratie is een aparte registratie die door de centrale
voorziening is ingericht en wordt onderhouden. De belangenregistratie is
opgenomen om het geraakte belang te bepalen per belanghebbende en de
contactgegevens die bij specifieke situaties van belang zijn. Deze worden bij
een geraakt belang uitgewisseld in de GebiedsinformatieLevering.

<div class="imageinfo ">
            <figure><img src="data/Images/EAID_9CA9590E_EF0B_4b57_A5CA_AA2BA4B3AFDD.png" usemap="#imagemap-EAID_9CA9590E_EF0B_4b57_A5CA_AA2BA4B3AFDD" alt="Diagram: 20b.IMKL-Belangenregistratie-WIBON - detail"><figcaption>Belangenregistratie WIBON: Belang en Veiligheidsgebied zijn beide beheerpolygonen. Een
Veiligheidsgebied heeft alleen contactpersonen voor de aanvraag. Het Belang
heeft daarnaast contactgegevens voor de graafmelding, calamiteitenmelding of
oriëntatieverzoek.</figcaption>
            </figure><map name="imagemap-EAID_9CA9590E_EF0B_4b57_A5CA_AA2BA4B3AFDD"><area shape="rect" alt="Organisatie" coords="390,786,618,1055" href="#global_class_LeveringGebiedsinformatie_Organisatie"><area shape="rect" alt="Beheerder" coords="97,655,346,892" href="#global_class_LeveringGebiedsinformatie_Beheerder"><area shape="rect" alt="AanvraagSoortContact" coords="940,742,1178,917" href="#global_class_LeveringGebiedsinformatie_AanvraagSoortContact"><area shape="rect" alt="Contact" coords="884,463,1089,603" href="#global_class_LeveringGebiedsinformatie_Contact"><area shape="rect" alt="Belang" coords="493,463,808,701" href="#global_class_LeveringGebiedsinformatie_Belang"><area shape="rect" alt="Veiligheidsgebied" coords="122,459,245,555" href="#global_class_LeveringGebiedsinformatie_Veiligheidsgebied"><area shape="rect" alt="BelangGeneriek" coords="448,64,741,373" href="#global_class_LeveringGebiedsinformatie_BelangGeneriek"><area shape="rect" alt="AanvraagSoortValue" coords="746,742,917,810" href="#global_class_IMKLBasis_AanvraagSoortValue"></map>
         </div>

<!-- ![](docs/media/20b.IMKL-Belangenregistratie-WIBON.png) -->
<!--
<figure id="afb_20b.IMKL-Belangenregistratie-WIBON">
    <img src="docs/media/20b.IMKL-Belangenregistratie-WIBON.png" alt="Belangenregistratie WIBON">
    <figcaption>Belangenregistratie WIBON: Belang en Veiligheidsgebied zijn beide beheerpolygonen. Een
Veiligheidsgebied heeft alleen contactpersonen voor de aanvraag. Het Belang
heeft daarnaast contactgegevens voor de graafmelding, calamiteitenmelding of
oriëntatieverzoek.</figcaption>
</figure>
-->

<!-- Figuur 5.14: -->

### Identifier management

<!--![](docs/media/identifiermanagement.png) -->

<figure id="afb_identificatie">
    <img src="docs/media/Identifier.png" alt="Afbeelding identificatie">
    <figcaption>Elementen van de IMKL object-identifier</figcaption>
</figure>

Identifiers van objecten worden in IMKL toegekend via het attribuut inspireId en
het datatype Identifier als het object vanuit INSPIRE beschreven is of met het
attribuut identificatie en het datatype NEN3610ID als het specifiek voor IMKL is
toegevoegd. Het toekennen van een inspireId betekent niet automatisch dat het
INSPIRE data-objecten betreft. Een voorbeeld waar dat niet het geval is, is het
thema Datatransport (telecommunicatie) waar de leiding en leidingelementen wel
een inspireId hebben maar het geen INSPIRE data-objecten betreft.

De systematiek voor het format van een identifier is gebaseerd op de combinatie
van een uniek benoemde namespace voor een applicatiedomein (of
organisatie-bronhouder) en unieke lokale id’s binnen een applicatiedomein. Omdat
voor utiliteitsnetten er vele bronhouders zijn is het niet mogelijk om met één
namespace te garanderen dat er in de combinatie van namespace en lokale
identifier, unieke identifiers ontstaan. Om toch met één namespace te kunnen
werken die het applicatiedomein representeert wordt het volgende voorstel
gedaan:

Namespace: ‘**nl.imkl’**

Format lokaalID: **bronhoudercode.lokaalID** (met een totaal van maximaal 255
tekens)

De namespace wordt geregistreerd in een nationaal namespace register.

De bronhoudercode is uniek en representeert de bronhouder van de gegevens en
wordt geregistreerd in een register van de nationale voorziening. Met de
bronhouder wordt niet bedoeld de mogelijke inwinner van de gegevens. De code
bestaat uit zes alfanumerieke posities. Dit is afgestemd met het format van CBS
codes voor gemeenten en provincies.

Het lokaalID maakt het mogelijk per bronhouder de objecten uniek te
identificeren. Het lokaalID is vrij door de bronhouder in te vullen en zal in de
meeste gevallen gelijk zijn aan het id in de lokale registratie.

**Extra toelichting.**

Identifiers hebben als functie objecten te kunnen aanwijzen en om aan objecten
te kunnen refereren. Ze maken een object uniek identificeerbaar. Als een
organisatie een identifier uitgeeft is deze binnen de organisatie wel uniek,
maar als datasets van verschillende organisatie worden samengevoegd tot een
nieuwe bestand is de identifier niet automatisch uniek in de nieuwe situatie. Om
binnen de nieuwe context identifiers uniek te maken is een systematiek nodig.
Binnen IMKL speelt dit op drie plaatsen:

1.  De individuele datasets van die verschillende bronhouders worden
    samengevoegd in IMKL. Om objecten binnen IMKL een unieke identificatie
    krijgen krijgt iedere bronhouder een code. De combinatie van bronhoudercode
    en interne identifier is dan uniek binnen IMKL. De interne identifier binnen
    de registratie van de bronhouder en de bronhoudercode worden aan elkaar
    geplakt met een ‘.’ ertussen tot een lokaalID.

2.  Het hele bestand van IMKL is slechts één van de datasets binnen INSPIRE. In
    INSPIRE worden identifiers uniek gemaakt door ze te voorzien van een
    namespace. Voor IMKL  is de namespace ‘nl.imkl’ bij INSPIRE als namespace
    geregistreerd.

3.  Sommige objecten van IMKL zijn geen onderdeel van de INSPIRE specificaties
    en kunnen dus ook geen INSPIRE Identifier krijgen. Deze objecten krijgen een
    NEN3610ID, die binnen de context van NEN3610 uniek is. Hiervoor is de
    namespace ‘nl.imkl’ ook binnen NEN3610 geregistreerd.
	
![](docs/media/VoorbeeldInspireID.png)

**Voorbeeld:** Een bronhouder heeft in eigen registratie een unieke identifier
‘xxyyzz’.  Binnen IMKL wordt hier een locaalId: ‘bb.xxyyzz’ van gemaakt.
Uitwisseling binnen INSPIRE van deze code zal er als volgt uitzien:

Omdat de identifiers die intern bij de bronhouders worden gebruikt op
verschillende manieren hergebruikt worden is er een aantal beperkingen op het
formaat van de identifiers. 

1.  De volgende karakters mogen in een lokaalID voorkomen: {”A”…”Z”, “a”…”z”,
    ”0”…”9”, “_”, “-“, “,”, ”.”}. “  (bron: NEN3610)

2.  INSPIRE had een vergelijkbare beperking op de structuur van identifiers,
    maar die is geschrapt.

3.  De afspraak dat een identifier binnen een GML document ook gebruikt wordt om
    een gml:id te construeren legt extra beperkingen op aan de identifier. Deze
    worden echter al afgevangen door de NEN3610 beperkingen.

In NEN3610 en INSPIRE kunnen identifiers ook nog voorzien zijn van een
versienummer van een object. Deze versies zijn van belang als er verschillende
(historische) versies van eenzelfde object onderscheiden moeten worden. Omdat
voor utiliteitsnetgegevens in IMKL alleen de huidige situatie wordt beschreven
zijn er geen verschillende versies van hetzelfde object in omloop. Daarom wordt
hiervoor in IMKL het versie attribuut niet gebruikt. Voor versies van een
GebiedsinformatieLevering of een Belang kunnen door het KLIC wel versienummers
worden gebruikt.

### Tijd representatie en temporeel model

IMKL hanteert de ISO 8601 norm voor het beschrijven van tijdsaspecten.

Binnen het informatiemodel IMKL zijn twee tijdsdimensies gemodelleerd, deze
worden in de volgende twee paragrafen beschreven.

**Temporele kenmerken in de werkelijkheid.**

In IMKL worden de temporele attributen ‘validFrom’ en ‘validTo’ van een object
gebruikt om de aanwezigheid van een object in de werkelijkheid te beschrijven.
Deze attributen worden gedefinieerd in INSPIRE. In de context van IMKL hebben ze
de volgende betekenis: 

-   'validFrom' beschrijft het tijdstip waarop het object in de werkelijkheid
    voor het eerst aanwezig is, en dus van belang is voor het voorkomen van
    graafschade. Geplande objecten kunnen een 'validFrom' tijdstip hebben dat in
    de toekomst ligt. Het attribuut 'validFrom' is verplicht. Wanneer van een
    object niet bekend is wanneer het is aangelegd voldoet een tijdstip waarop
    geconstateerd is dat het object er is.

-   ‘validTo’ beschrijft het tijdstip vanaf wanneer het object niet meer in de
    werkelijkheid voorkomt. Dit attribuut is optioneel; wanneer het niet is
    ingevuld betekent dit dat er vooralsnog geen tijdstip bekend is waarop de
    geldigheid van dit object eindigt.

**Temporele kenmerken in de registratie.**

Naast het beschrijven van de levensduur van het object in de werkelijkheid zijn
er ook attributen die beschrijven wanneer het object bekend is in de
registratie: 'beginLifespanVersion' en 'endLifespanVersion' beschrijven de
geldigheid van een versie van een object in de registratie. Omdat IMKL een
doorgeefluik is van de registraties van de netbeheerders gaat het om de
tijdstippen van registratie bij de netbeheerder. Volgens NEN3610 ontstaat er een
nieuwe versie van een object wanneer de waarde van een attribuut van dat object
wijzigt, dit betekent dat bij een wijziging van een attribuut een object een
nieuwe versie ontstaat en dus beginLifespanVersion vernieuwd wordt. Omdat in
IMKL alleen de huidige situatie wordt beschreven zal in alle gevallen het
'endLifespanVersion' van het object leeg zijn.

**Voorbeelden**

Een aantal voorkomende gevallen wordt hieronder met een voorbeeld uitgewerkt:

-   Op 2 september 2016 wordt een kabel gelegd. Dit wordt een dag later (3
    september 2016) in de computer ingevoerd.  
    { validFrom='2016-09-02' validTo=  beginLifespanVersion='2016-09-03'}

-   Op 31 december 2015 wordt de status van een kabel die er al sinds 5 april
    1968 lag in 'disused' veranderd. Dit wordt op 3 januari 2016 ingevoerd.  
    { validFrom='1968-04-05' validTo=  beginLifespanVersion='2016-01-03
    currentStatus='disused'}

-   Op 6 mei 2014 wordt besloten dat er op 1 juli 2014 een leiding in de grond
    gelegd wordt.  
    { validFrom='2014-07-01' validTo=  beginLifespanVersion='2014-05-06'
    currentStatus='projected'}

-   Op 15 december 2013 wordt besloten dat op 21 december 2013 een kabel die er
    sinds 2 juni 2006 lag uit de grond gehaald zal worden.  
    { validFrom='2006-06-02' validTo='2013-12-21'
    beginLifespanVersion='2014-12-15'}

Merk op dat het met de huidige modellering niet mogelijk is een geplande
statuswijziging uit wisselen. Dit komt omdat er van ieder object slechts 1
versie wordt uitgewisseld en bij een geplande wijziging is er sprake van twee
versies: de huidige en de gepland. Geplande aanleg en verwijdering kunnen wel
uitgewisseld worden omdat er dan slechts 1 versie hoeft te worden uitgewisseld.
