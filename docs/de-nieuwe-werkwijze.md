---
layout: page-with-side-nav
title: De nieuwe werkwijze
---
# De nieuwe werkwijze

In  3 Het drie-lagen model  is al uitgelegd hoe SIM's, UGM's en BSM's met elkaar verweven zijn. In dit hoofdstuk beschrijven we hoe deze modellen daadwerkelijk vervaardigd 
kunnen worden. Als handige start kan het [template Enterprise Architect bestand](https://kinggemeenten.plan.io/attachments/162056) als basis worden genomen. Dit bevat een 
initiële folder structuur en verder alleen modellen die je nodig zou kunnen hebben, bijv. modellen voor datatypes en berichtsoorten.

Bij het verwerken van de vervaardigde modellen met Imvertor kunnen er foutmeldingen en waarschuwingen optreden. Voor goedkeuring dient elk model vrij te zijn van 
foutmeldingen en waarschuwingen. Een lijst met de meeste mogelijke foutmeldingen kan  "hier":https://imvertor.armatiek.nl/imvertor-executor/dashboard/wikis/msg gevonden 
worden. Ook in hoofdstuk  8 Veel voorkomende fouten  vind je een aantal veel voorkomende fouten en een uitleg hoe daarmee om te gaan.

[**4.1. Modellenbeheer**](#41-modellenbeheer)

[**4.2. Het opstellen van een horizontaal Semantisch InformatieModel**](#42-het-opstellen-van-een-horizontaal-semantisch-informatiemodel)

[**4.3. Het opstellen van een horizontaal GegevensUitwisselingsModel**](#43-het-opstellen-van-een-horizontaal-gegevensuitwisselingsmodel)

[**4.4. Het opstellen van een koppelvlak**](#44-het-opstellen-van-een-koppelvlak)

## 4.1. Modellenbeheer

[**Terug naar top**](#4-de-nieuwe-werkwijze)

In dit hoofdstuk beschrijven we hoe we binnen VNG-realisatie i.h.k.v. de Nieuwe Aanpak omgaan met het beheer van onze modellen. Het aantal modellen dat we in beheer hebben 
neemt vlug toe en aangezien de relaties tussen deze modellen een spaghetti aan afhankelijkheden oplevert is het van groot belang dat de procedure voor het gezamenlijk werken 
aan deze modellen voor iedereen duidelijk is en ook toegepast wordt.
Omdat bij dat beheer SVN een centraal onderdeel is zijn hieronder de belangrijkste SVN handelingen beschreven. In de paragraaf daaronder beschrijven we de te hanteren 
procedure waarbij je gebruik maakt van de beschreven SVN handelingen.

### 4.1.1. Het gebruik van SVN

Randvoorwaarde om SVN binnen Enterpise Architect te kunnen gebruiken is dat Tortoise SVN geïnstalleerd is en en dat Enterprise Architect is geconfigureerd om de repository 
met Informatiemodellen, Gegevensmodellen en Berichtmodellen te kunnen gebruiken. Zie onder  1 Installatie  de paragraaf  **SVN configureren voor EA**.

#### Het vastleggen van een nieuw model (package) in de repository

Als er een nieuw model wordt gemaakt in Enterprise Architect, om het even of dat nu een SIM, UGM of BSM is, en dat model moet opgenomen worden in de SVN-repository, dan moet 
op het niveau van de model-package aangegeven worden dat deze package opgenomen moet worden in de repository. 
* Selecteer de betreffende package en kies via de linkermuis-knop de keuze 'Package Control' en in het Sub-menu de keuze 'Configure'. 
* Kies in het pop-up menu de keuze 'Configure'. 
* Klik het vinkje bij 'Control Package' aan.
* Selecteer bij  Version Control de repository die bij het installeren van SVN is geconfigureerd. (Met het pijltje aan de rechterkant van de het invoerveld.  
* Voer bij XMI Filename de bestandsnaam in waarmee deze package opgeslagen. 
* Klik op 'OK'. 

![Package Control Options][PackageControlOptions]

> In Enterprise Architect 15.1 kan dit menu gevonden worden via het menu **Publish > Model Exhange > Package Control > Configure > Package Control...**.

De bestandsnaam voldoet daarbij aan de volgende conventie: *[Modeltype] [Domein (al dan niet als afkorting)].xml*

Modeltype is daarbij gelijk aan 'SIM', 'UGM' of 'BSM'. Enkele voorbeelden hiervan zijn 'SIM RSGB.xml' of 'BSM Bevraging Bewoning.xml'.

#### Het ophalen van een bestaand model (package).

Randvoorwaarde voor het ophalen van een model uit de repository in Enterprise Architect is dat er een standaard projecten structuur aanwezig is in het EA-bestand. Om te 
waarborgen dat dit het geval is dien je bij het aanmaken van een nieuw EA bestand een kopie te maken van het EA Template bestand dat je kunt vinden in de folder die je 
n.a.v. de tweede bullet van de sectie [SVN configureren voor EA](https://kinggemeenten.plan.io/projects/de-nieuwe-aanpak/wiki/1_Installatie#section-10) hebt aangemaakt of 
gekozen.

Het ophalen van een model wordt gedaan door een Get package uit te voeren: 

* Selecteer de project-package waaronder het model moet worden opgenomen.
* Ga via de linkermuisknop naar de menukeuze "Package Control" en selecteer in het sub-menu "Get Package...".
* Selecteer de locatie waar het gewenste model is opgeslagen. De locaties die hier beschikbaar zijn zijn bij het configureren van Version Control in EA aangebracht (zie 
hoofdstuk 1: [SVN configureren voor EA](https://kinggemeenten.plan.io/projects/de-nieuwe-aanpak/wiki/1_Installatie#section-10)).
* Selecteer het model dat je vanuit de repository in Enterprise Architect beschikbaar wilt hebben en klik op "OK".

Het model wordt nu binnengehaald  en onder de package gezet die  je in de eerste stap hebt geselecteerd.

> **Let op**: Het binnenhalen van een stelsel aan packages dient in de juiste volgorde te gebeuren. Dus eerst de SIM packages waar andere SIM packages van afhankelijk zijn, 
daarna die andere SIM packages en daarna hetzelfde voor de UGM packages en tenslotte het BSM package. Voor het bepalen van de juiste volgorde verwijs ik naar 
[het Supplieroverzicht](https://vvng.sharepoint.com/sites/UnitArchitectuurenStandaarden/Gedeelde%20documenten/General/De%20nieuwe%20aanpak/Supplieroverzicht.html). De in dit 
overzicht op het laagste niveau voorkomende modellen (de modellen die het verste inspringen) moeten als eerste binnengehaald worden.

#### Bewerken van een model

Een model dat is opgehaald is altijd ingechecked. Als je een model wilt bewerken moet je het uitchecken. Dat doe je als volgt:
* Selecteer het model-package dat je wilt wijzigen. 
* Ga via de linkermuisknop naar de menukeuze "Package Control" en selecteer in het sub-menu "Check Out...".
De meest recente versie van het model wordt nu binnengehaald  (dat is dus eigenlijk meteen een "Get Latest") en opengezet voor het aanbrengen van wijzigingen. 
Ook wordt het model gelocked voor wijzigingen door anderen. Het is dus raadzaam om modellen niet onnodig uitgechecked te laten staan. Tevens voorkomt dat problemen als je 
het package ook in een ander EA bestand gebruikt en het zonder daar erg in te hebben ook daar zou uitchecken.

Na het aanbrengen van de wijzigingen kan je het model weer inchecken en dat doe je als volgt :
* Selecteer het model-package dat je wilt inchecken.
* Ga via de linkermuisknop naar de menukeuze "Package Control" en selecteer in het sub-menu "Check In...".

#### Raadplegen van een model.

Modellen die je opgenomen hebt in je EA-bestand worden niet automatisch bijgewerkt. Op het moment dat iemand anders in een model een wijziging heeft aangebracht moet die 
wijziging pro-actief opgehaald worden. Je kunt de laatste versie van een specifiek model ophalen door het volgende te doen.
* Selecteer het model-package dat je wilt updaten. 
* Ga via de linkermuisknop naar de menukeuze "Package Control" en selecteer in het sub-menu "Get Latest...".

Als je alle modellen die in jouw EA-betand zitten wilt updaten (aanrader) dan kies je in de bovenstaande situatie voor de keuze "Get All Latest".

#### Verwijderen van modellen

Indien je een model uit je EA-bestand wilt verwijderen kan dat door de package te verwijderen. 
* Selecteer het model-package dat je wilt verwijderen. 
* Ga via de linkermuisknop naar de menukeuze "Delete (Packagenaam)".

> **Let op**: een model dat in  Version Control is opgenomen kan later weer opgehaald worden (zie boven). Echter een model of package dat niet in Version Control is 
opgenomen wordt hiermee definitief verwijderd en is niet meer terug te halen. 

> **Let op 2**: Pas wel op met de volgorde van weggooien en vooral inladen. Als je een model verwijderd waarnaar vanuit een ander model verwezen wordt dan zijn in 
laatstgenoemd model in de diagrammen de verwijzingen naar eerstgenoemd model weg. Deze verwijzingen komen niet meer terug. Dus als je zo'n eerstgenoemd model verwijderd, 
verwijder dan eerst alle modellen die daarnaar verwijzen en laad ze (indien gewenst)  'van boven naar beneden' weer opnieuw in.

#### Updaten van modellen

De meeste modellen hebben een afhankelijkheid van andere modellen. Op die andere modellen vindt beheer plaats en het kan dus voorkomen dat je n.a.v. het beschikbaar komen 
van een nieuwe versie in je EA bestand de oude versie van een model moet vervangen door een nieuwe versie van datzelfde model. In principe wordt van elke versie een tag 
vastgelegd (zie volgende hoofdstuk) en vervangen van een model betekent dus eigenlijk dat je een model dat verwijst naar een specifieke tag verwijdert en de nieuwe tag 
voor dat model weer inleest.
De modellen zijn echter d.m.v. traces aan elkaar gelinkt en bij het vervangen van een model wil je niet dat deze traces verloren gaan. Om dat te voorkomen moet je de 
volgende procedure hanteren:

1. Check eerst alle modellen die je in het EA bestand hebt uitgecheckt weer in;
2. Verwijder nu het te vervangen model;
3. Lees de nieuwe tag in;
4. Voer een 'Get All Latest' uit.

Daarmee is de nieuwe versie weer beschikbaar in EA en zijn de traces behouden. Nu dien je je eigen model(len) weer in lijn te brengen met het zojuist vervangen model.

### 4.1.2. Procedure modellenbeheer

Zie ook het bijgaande [Presentatie Procedure modellenbeheer](https://kinggemeenten.plan.io/attachments/161227). Deze presentatie is echter slechts ter ondersteuning, de 
onderstaande procedure is in die zin normatief.

#### Opbouwen EA modellen structuur

Het is bij het laden van de benodigde modellen van groot belang dat je de modellen in de juiste volgorde in EA ophaalt. Om die reden dien je voordat je gaat ophalen een 
goed beeld te hebben van de benodigde modellen en van de volgorde van ophalen. Hiervoor is de tabel 'Tags model-supplier overzicht' die je 
[hier](https://vvng.sharepoint.com/sites/UnitArchitectuurenStandaarden/Gedeelde%20documenten/General/De%20nieuwe%20aanpak/Supplieroverzicht.html) vindt onontbeerlijk. Deze 
tabel wordt regelmatig ververst dus het is verstandig dit bestand steeds weer opnieuw te downloaden. Welke modellen je nodig hebt is o.a. afhankelijk van de rol waarin je 
een model gebruikt. 

Indien je als beheerder een bestaand model gaat bewerken dan moet je dat model zoeken in de 'trunk' of in de 'branches' folder van de repository. Wil je van scratch af aan 
een nieuw model gaan opbouwen dan haal je geen model op uit de trunk' of 'branches' folder maar dan ga je juist een nieuw model in de trunk plaatsen.
Over het algemeen zul je echter de meeste modellen alleen als gebruiker op willen halen. Dit zijn de modellen waar jij zelf niet verantwoordelijk voor bent en in dat geval 
zoek je in de 'tags' folder en daarvoor is de eerder genoemde tabel handig. Je mag er trouwens vanuit gaan dat de modellen die in de tags folder staan ook aanwezig zijn op 
de Imvertor server. De eigenaar van een model heeft immers de verantwoording om dat model op de Imvertor server te processen voordat hij/zij een verzoek tot het aanmaken 
van een tag plaatst.

1. Bij het maken van het overzicht begin je bij het model dat je wil gaan bewerken. Bepaal aan de hand van de tabel of, als het model nog niet in de tabel is opgenomen, 
2. zelfstandig van welke versie van modellen je model afhankelijk is of afhankelijk moet worden; 
3. Bepaal vervolgens van welke modellen deze gevonden modellen afhankelijk zijn;
4. herhaal de voorgaande stap totdat er geen modellen meer zijn die afhankelijk zijn van andere modellen;
5. Nu ga je de modellen die je gevonden hebt één voor één binnenhalen in EA, te beginnen bij de laatst gevonden modellen. Over het algemeen zul je eerst de SIM modellen 
6. binnenhalen, daarna (indien van toepassing) de UGM modellen en tenslotte (wederom indien van toepassing) de BSM modellen;
7. Dit herhaal je vervolgens weer totdat je bij het model dat je wil bewerken of, als dat model nog niet bestaat, bij de modellen waar deze afhankelijk is bent aangekomen;
8. je bent nu klaar om in EA te gaan werken.

#### Het aanvragen en vervaardigen van een tag

Binnen SVN maken we gebruik van tags om een opname te maken van onze modellen op een formeel moment. Een voorbeeld van zo'n moment is de start van een openbare consultatie 
maar het kan ook zijn dat je je model rijp genoeg acht voor het eerste gebruikt door je collega's. Een tag is altijd een read-only bestand. Op een tag kunnen dus geen 
wijzigingen meer worden aangebracht. Zitten er fouten in een tag dan is de enige remedie deze te vervangen door een andere tag. Voorwaarde voor het vervaardigen van een 
tag is dat deze minimaal foutvrij door Imvertor komt.

Zo ga je te werk:
1. Zorg er voor dat je je model hebt ingecheckt. Het staat dus in de 'trunk' of 'branches' folder;
2. Verwerk het model nog eenmaal met Imvertor. Dit zorgt er voor dat er voor elke tag een overeenkomend model op de Imvertor server is;
3. Stuur een verzoek voor het aanmaken van een tag naar de administrator van de NieuweAanpak (NA) repository en verstrek deze daarbij de volgende informatie:
  * De bestandsnaam van het te taggen model;
  * Het versienummer van het te taggen model in het volgende formaat nn_nn_nn;
  * De releasedatum van het te taggen model (*Let op!* dit is de waarde van de tagged value 'release' die op het package gedefinieerd is);
  * De status van het te taggen model. We kennen de volgende statussen: (Wellicht nog niet compleet)
    * In ontwikkeling
    * In beoordeling
    * Gereed voor UGM
      Deze status wordt alleen gebruikt bij een SIM. Hiermee geef je aan dat je nog wel aan het werk bent in de SIM maar dat hij voldoende gereed is om te worden verwerkt 
      tot een SIM. Een SIM hoeft niet verplicht deze stap te doorlopen. 
    * In gebruik
  * In geval van een geheel nieuw model een lijstje met modellen waar het nieuwe model van afhankelijk is. 
4. Na ontvangst van het verzoek zal de administrator de tag aanmaken. Daarbij hanteert hij als het origineel in de trunk staat de volgende naamgevingsconventie: 
   *[bestandsnaam in de trunk minus de extensie] [versienummer] [status] R[releasedatum].xml*
   of als het origineel in de branch staat: *[bestandsnaam in de branch minus de datum en extensie] R[releasedatum].xml*;
5. Nadat de tag is vervaardigd stelt de administrator de opdrachtgever op de hoogte. De opdrachtgever zal vervolgens het origineel van het model (in de 'trunk' of 'branches' 
   folder) openen in EA en de taggedvalue 'releasedatum' een nieuwe waarde geven. Daarmee wordt voorkomen dat het met de zojuist gemaakte tag overeenkomende model op de 
   server overschreven wordt;
7. De administrator verwerkt de nieuwe tag en ook een evt. nieuw model in de trunk in de eerder genoemde tabel;
8. Tenslotte informeert de administrator zo nodig alle gebruikers van een voorgaande versie van het model dat er een nieuwe versie voor handen is.
9. Om de hoeveelheid bestanden in de tags te beperken wordt er naar gestreefd oude tags zo snel mogelijk op te ruimen. Na een periode van uiterlijk 2 maanden wordt een oude 
   tag verwijderd. NB. doordat de oudere tag nog in het versiebeheersysteem op te vragen is gaat er niets verloren. Alleen blijft het aantal versies van tags beperkt tot de 
   actuele versies zodat e.e.a. overzichtelijk blijft.

#### Het aanvragen van een branch

Branches worden vervaardigd om versies van modellen met de status 'in gebruik' apart op te slaan teneinde evt. patches te kunnen ontwikkelen. Dit kan dus (in principe) alleen met modellen die in de trunk de status 'in gebruik' hebben bereikt. Hier is de voorwaarde dat het model fout- en waarschuwingsvrij door Imvertor komt.

Hoe ga je te werk.
1. Zorg er voor dat je je model met de status 'in gebruik' hebt ingecheckt. Het staat dus in de 'trunk' folder;
2. Verwerk het model nog eenmaal met Imvertor. De laatste controle dat deze foutvrij is en dat er voor de later in deze procedure vervaardigde tag een overeenkomend model
   op de Imvertor server is;
3. Stuur een verzoek voor het aanmaken van een branch naar de administrator van de NieuweAanpak (NA) repository en verstrek deze daarbij de volgende informatie:
  * De bestandsnaam van het te branchen model;
  * Het versienummer van het te branchen model in het volgende formaat nn_nn_nn.
  * De releasedatum van het te branchen model (dit is de waarde van de tagged value 'release' die op het package gedefinieerd is);
4. Na ontvangst van het verzoek zal de administrator de branch aanmaken. Daarbij hanteert hij de volgende naamgevingsconventie: 
   *[bestandsnaam in de trunk minus extensie] [versienummer] in gebruik [datum branchcreatie].xml*;
5. De administrator zal daarna, als dat niet al eerder is gebeurd, tevens een nieuwe tag aanmaken. Daarbij hanteert hij de volgende naamgevingsconventie: 
   *[bestandsnaam in de trunk minus extensie] [versienummer] in gebruik R[releasedatum].xml*;
6. Nadat de branch is vervaardigd stelt de administrator de opdrachtgever op de hoogte. De opdrachtgever zal vervolgens het origineel van het model in de 'trunk' folder 
   openen in EA en de taggedvalue 'releasedatum' een nieuwe waarde geven. Daarmee wordt voorkomen dat de met de zojuist gemaakte branch overeenkomende model op de server 
   overschreven wordt. Tevens zal hij de status van het model weer op 'in ontwikkeling' zetten. Zo mogelijk kent de opdrachtgever ook een nieuwe waarde aan het 'Version' 
   property toe;
7. De opdrachtgever zal vervolgens de zojuist gemaakte branch van het model in de 'branches' folder openen in EA en de taggedvalue 'releasedatum' een nieuwe waarde geven. 
   Daarmee wordt voorkomen dat het met de zojuist gemaakte tag overeenkomende model op de server overschreven wordt zodra men de branch gaat gebruiken om een patch te creëren. 
   Tevens zal hij de status van het model weer op 'in ontwikkeling' zetten;
8. De administrator verwerkt de nieuwe branch en ook de nieuwe tag in de eerder genoemde tabel;
9. Tenslotte informeert de administrator zo nodig alle gebruikers van een voorgaande versie van het model dat er een nieuwe versie voor handen is.

## 4.2. Het opstellen van een horizontaal Semantisch InformatieModel

[**Terug naar top**](#4-de-nieuwe-werkwijze)


> **Noot** Dit hoofdstuk moet nog verder worden ingevuld.

Een horizontaal Semantisch Informatiemodel (ook wel Conceptueel Informatiemodel genoemd) is een modellering van de realiteit van objecten  die een meervoudige toepassing 
kennen. De objecten in zo'n model hebben dus in meerdere domeinen een toepassing. Door deze objecten in een horizontaal Semantisch Informatiemodel te definiëren zorgen we er 
voor dat niet steeds opnieuw het wiel uitgevonden hoeft te worden en dat ze overal waar ze gebruikt worden op eenzelfde wijze worden gespecificeerd.

## 4.3. Het opstellen van een horizontaal GegevensUitwisselingsModel

[**Terug naar top**](#4-de-nieuwe-werkwijze)


In een horizontaal GegevensUitwisselingsmodel worden die gegevens op UGM niveau uitgewerkt die een meervoudige toepassing kennen. Als in een verticaal 
GegevensUitwisselingsModel dan wordt verwezen naar entiteiten en attributen uit een horizontaal GegevensUitwisselingsModel zorgt dat er voor dat deze gegevens in alle 
koppelvlakken (ongeacht of dat nu gaat om een StUF of een REST JSON koppelvlak) op eenzelfde wijze worden gespecificeerd.

Zoals in hoofdstuk [Het drie-lagen model](...)  al is uitgelegd zijn SIM's en UGM's sterk met elkaar verweven.
In het geval van een UGM kan die verwevenheid initieel al voor een groot deel geautomatiseerd worden vastgelegd.
Voer daarvoor de werkinstructie 'Werkinstructie SIM omzetten naar UGM' zoals beschreven in [Werkinstructies](Werkinstructie-SIM-omzetten-naar-UGM) uit. 
Dit zorgt er voor dat alle stereotypes die in feite nog tot het MIG behoren worden omgezet naar stereotypes die tot het MUG behoren.
Zo krijgt een class met het stereotype 'Objecttype' het stereotype 'Entiteittype' toegekend en een attribuut met het stereotype 'Attribuutsoort' het stereotype 'Element'. 
Daarnaast worden er automatisch traces gecreëerd tussen de gerelateerde componenten in het SIM en het UGM.

Het UGM is daarmee bijna klaar om verder verwerkt te worden tot een volwaardig UGM. Dat wil zeggen dat voor SIM logische structuren omgezet worden naar structuren die 
technisch beter verwerkt kunnen worden. Dat gebeurd op basis van een aantal  421 Technische en implementatie-overwegingen . Eerst moeten er echter een aantal handelingen 
uitgevoerd worden die onafhankelijk zijn van de gewenste uitvoer (yaml of StUF) en een aantal handelingen die specifiek zijn voor de gewenste uitvoer.

### 4.3.1. Generieke handelingen

Om Imvertor in staat te stellen de gelegde traces te interpreteren moet duidelijk zijn naar welke modellen de traces leiden. Voer daarvoor de volgende handelingen uit:
* Definieer op het zojuist vervaardigde package (het nieuwe UGM model) de volgende tagged values:
  * **Supplier-name**: ken hieraan de naam van het package toe waar het UGM van is afgeleid. Is het UGM van meerdere packages (SIM of UGM)  afgeleid plaats dan alle namen in 
    deze tagged value van elkaar gescheiden door een ';' (punt komma);
  * **Supplier-project**: ken hieraan de typeindicatie van de package waar het UGM van is afgeleid. Is het UGM van meerdere packages afgeleid dan plaats je ook hier meerdere 
    type indicaties wederom van elkaar gescheiden door een ';' (punt komma). Let er op dat de volgorde van de packages gelijk moet zijn aan die in de tagged value 
    'Supplier-name';
  * **Supplier-release**: ken hier tenslotte de release van de package waar het UGM van is afgeleid. Het gaat dus om de tagged value 'Release' in dat betreffende packages. 
    Ook nu geldt weer dat je meerdere 'release' waarden kunt plaatsen mits ze maar gescheiden zijn door een ';' (punt komma) en in dezelfde volgorde staan als in de 
    voorgaande twee tagged values.

Voer vervolgens de volgende acties uit:

* Creëer de tagged value 'Release' en ken daar een waarde aan toe met de volgende conventie 'yyyymmdd';
* Ken aan de property 'Version' op het  UGM package een waarde toe met het volgende patroon 'nn.nn.nn' waarbij 'nn' een numerieke waarde is. Bijvoorbeeld '00.00.01';
* Ken voor elke SIM waarvan het UGM is afgeleid de tagged value 'Versienummer SIM [naam oorspronkelijke SIM]' aan het UGM package toe. Geef deze tagged values als waarde de 
  waarde van de property 'Version' van de betreffende SIM's, Dit is alleen ter documentatie;
* Ken voor elke UGM waarvan het UGM is afgeleid de tagged value 'Versienummer UGM [naam oorspronkelijke UGM]' aan het UGM package toe. Geef deze tagged values als waarde de 
  waarde van de property 'Version' van de betreffende UGM's, Ook dit is alleen ter documentatie;
* Creëer zo gewenst nieuwe packages voor Groepen, Complexdatatypes, etc... of hernoemd bestaande packages.
  Dit is niet perse noodzakelijk maar slechts ter ordening _<-- Indien we bij SIM standaard package namen hanteren dan kunnen deze omgezet worden naar de in het UGM te 
  hanteren namen. Dat vergt nog een aanpassing in het script van Geert_;
* Plaats indien van toepassing alle objecten in de zojuist aangemaakte packages;
* Wijzig alle stereotypes 'Tabel Element' in 'Element'. _<-- Script genereert nu nog verkeerde stereotype <<Tabel element>> in plaats van <<Element>>. Vergt nog een 
  aanpassing in het script van Geert_;
* Hernoem alle stereotypes 'Groep' naar 'Groep compositie'. _<-- Zit niet in script ??en in MUG profiel??. Vergt nog een aanpassing van het script van Geert_;
* Voorzie de tagged value 'Formeel patroon' van een valide regular expression indien de tagged value 'Patroon' een waarde heeft;
* Zorg dat alle attributen een type hebben;
* Zoek, indien de typering van attributen verwijst naar tabel-entiteiten of enumeraties in een SIM buiten het eigen model, in andere UGM modellen naar het gerelateerde 
  tabel-entiteit of enumeratie en kopieer dat naar je eigen UGM;
* Herstel de traces vanuit de zojuist gekopieerde tabel-entiteiten en enumeraties (afhankelijk van hoe je dat wil naar het SIM of naar het UGM waaruit ze vandaan komen);
* Ken de nieuwe tabel-entiteiten en enumeraties toe aan de attributen in jouw model waarop ze betrekking hebben;
  Voorzie attributen die geen type hebben van een type. Vaak zijn dit types die voorheen het stereotype attribuutsoort_proxy hadden;
* Wijzig op het UGM package het 'Keyword' veld in 'UGM';

> **Vraag**: Wat is hiervan de functie?

* Pas, indien gewenst, op het UGM package het 'Author' veld aan.

### 4.3.2. Handelingen t.b.v. de generatie van yaml schema's

De volgende handelingen zijn alleen van toepassing indien het uiteindelijke doel het genereren van yaml schema's is:

* Wijzig de traces van de proxy objecten, de proxy groepen en hun proxy attributen zo dat ze verwijzen naar de objecten en attributen in het gerelateerde SIM.
* Pas aan de hand van de volgende omzettingstabel de stereotypes van de proxy objecten, de proxy groepen en hun proxy attributen aan. Doe dat zodanig dat je de oude 
  stereotypes er eerst van verwijderd.

| Stereotype SIM | Stereotype UGM |
| --- | ---|
| Objecttype_proxy | Entiteittype |
| Gegevensgroep_proxy | Groep compositie |
| Attribuutsoort_proxy | Element |

* Geef de oude proxy objecten, proxy groepen en hun proxy attributen gewenste namen;
* Herschrijf namen met unsupported characters zoals /;

> **Noot**: Nagaan of dit soort karakters niet door Imvertor worden verwijderd. Indien dat het geval is dan is deze handeling niet noodzakelijk al kan je er voor 
  kiezen om in het UGM de juiste benamingen te gebruiken.

* We streven naar een UGM dat qua naamgeving 1 op 1 overeenkomt met de in yaml gebruikte naamgeving. Verwijder daarom eventuele spaties en vreemde karakters uit de 
  enumeraties. Alleen de tekens a-z, A-Z en underscore zijn toegestaan;
* Desambigueer duplicate relatienamen;

> **Noot**: Nagaan of dit nodig is voor yaml. Zo ja dan kan deze handeling naar de generieke handelingen. Deze handeling moet dan ook uit de 
  andelingen voor StUF gehaald worden.

* Maak daar waar gewenst relaties bi-directioneel of inverteer deze. Anders kun je op het moment dat je met het BSM aan de slag gaat niet de inverse richting op in 
  schema composer. 

> **Noot**: Nagaan of dit nodig is voor yaml.

* Ken de volgende tagged values toe:
  * Aan alle entiteiten 'Naam in meervoud' met een waarde die gelijk is aan het meervoud van de naam van de resource.
  * Aan alle relaties 'target role in meervoud' met een waarde die gelijk is aan het meervoud van de naam van de resource waarnaar verwezen wordt. Als er meerdere 
    relaties naar dezelfde resource verwijzen dan moet deze tagged value gedifferentieerd worden.

> **Vraag**: Waaraan moet de naamgeving van deze tagged values voldoen. Het gaat me niet zozeer om het patroon maar meer of in de naam ook de semantiek van de 
  relatie tot uiting moet komen. Dus moet het 'medewerkers' zijn of 'contactvoerendemedewerkers'? Bij meerdere relaties naar dezelfde resource lijkt me de laatste 
  i.i.g. van toepassing.

### 4.3.3. Handelingen t.b.v. de generatie van StUF schema's

De volgende handelingen zijn alleen van toepassing indien het uiteindelijke doel het genereren van StUF schema's is:

* Pas de alias van het UGM package aan naar de namespace waarin de XML-schema's moeten komen. Dit kan een nieuwe namespace zijn maar ook een al bestaande;
* Ken de tagged value 'Verkorte alias' toe aan het UGM package. Deze is gelijk aan de prefix die je in de XML-schema's wil gebruiken;
* Wijzig de traces van de proxy objecten, de proxy groepen en hun proxy attributen zo dat ze verwijzen naar de objecten en attributen in het gerelateerde SIM of naar 
  entiteiten en attributen in een ander UGM. Stel jezelf daarbij de vraag in welke namespace je de entiteiten, de groepen, de attributen van de entiteiten, groepen, 
  relaties en tabel-entiteiten geplaatst wil hebben. Is dat in de namespace van het UGM dat je nu aan het creëren bent laat dan de traces lopen naar het SIM waarvan 
  het UGM is afgeleid. Is dat in de namespace van het UGM dat verbonden is met de SIM waar de proxies naar verwijzen zet dan de traces om naar de entiteiten, de 
  groepen en de attributen van die entiteiten, groepen, relaties en tabel-entiteiten in dat UGM.
* Pas aan de hand van de volgende omzettingstabel de stereotypes van de proxy objecten, de proxy groepen en hun proxy attributen aan. Doe dat zodanig dat je de oude 
  stereotypes er eerst van verwijdert.

|_. Stereotype SIM |_. Stereotype UGM |
| Objecttype_proxy | Entiteittype |
| Gegevensgroep_proxy | Groep compositie |
| Attribuutsoort_proxy | Element |

* Indien je de proxy objecten, de proxy groepen en hun proxy attributen hebt laten tracen naar een ander UGM, wijzig dan de namen van deze componenten ook zo dat ze 
  overeen komen met de namen die ze in het met de proxy objecten gerelateerde UGM hebben. Indien je ze hebt laten tracen naar het met het UGM gerelateerde SIM dan 
  kun je je eigen namen bedenken;
* Herschrijf namen met unsupported characters zoals /;

> **Noot**: Nagaan of dit soort karakters niet door Imvertor worden verwijderd. Indien dat het geval is dan is deze handeling niet noodzakelijk al kan je er voor 
  kiezen om in het UGM de juiste benamingen te gebruiken.

* Verwijder zo nodig de spaties uit enumeraties (p{color:red};

> **Noot**: Volgens mij zijn spaties in enumeraties in XML-Schema wel toegestaan. Indien dat zo is dan is bovenstaande handeling niet nodig.

* Desambigueer duplicate relatienamen;
* Pas de aliassen aan van de entiteittypen, relaties, relatie-entiteiten en tabel-entiteiten. 
  * Zorg er ook voor dat de aliassen van die relaties onderling afwijken door er een 9 letterige mnemonic van te maken;
  * Relatie-entiteiten krijgen dezelfde alias als de relatie waarmee ze verbonden zijn;
* Maak daar waar gewenst relaties bi-directioneel of inverteer deze. Anders kun je op het moment dat je met het BSM aan de slag gaat niet de inverse richting op in 
  schema composer. 
* Voorzie indien nodig de tagged values 'Historie materieel' en 'Historie formeel' van een waarde;
* Kijk waar attributen in de supplier horizontale sectormodellen uit andere entiteiten komen (ze zijn daar dus platgeslagen) en voorzie die in de naam van de prefix 
  die gelijk is met de mnemonic van de oorspronkelijke entiteit gevolgd door een punt;
* Kijk waar groepen zijn platgeslagen in de horizontale sectormodellen. Doe dat ook in het UGM;
* Verwijder de zojuist platgeslagen groepen;
* Herstel traces van platgeslagen attributen;
* Kijk welke attributen matchgegevens moeten zijn. Stel bij die attributen de tagged value 'Indicatie matchgegeven' in op 'Ja' en definieer die attributen ook als 
  zijnde 'Static' waardoor deze onderstreept worden. Alle id attributen zijn matchgegevens dus daar moeten deze wijzigingen sowieso worden aangebracht.
* Corrigeer de volgorde van attributen in entiteiten indien deze niet gelijk zijn aan die in horizontale sectormodellen en dat is wel gewenst is.

**NB**: Eigenlijk moeten een aantal handmatige stappen al in het SIM geregeld zijn, want nu moet het elke keer handmatig overnieuw gedaan worden.

### 4.3.4. Technische en implementatie-overwegingen

Hier kunnen we documenteren welke overwegingen er zijn toegepast bij het opstellen van het UGM. Daarbij kan gebruik gemaakt worden van voorbeelden. 

In mijn beleving wordt dit hoofdstuk wat vroeger het "verStUFfingsdocument"  was.

> **Noot**: Nee, dat klopt niet. Hier wordt uitgelegd wat de gedachte achter de creatie van een UGM is (in feite ook de gedachte achter het 
  verStUFfingsdocument). In de volgende paragrafen moet dan uitgelegd worden welke methodes er bij het creëren van een UGM kunnen worden gehanteerd. Het zou kunnen 
  dat deze pagina voor het yaml deel uiteindelijk vervangen wordt door de API Best Practices. Op zijn minst voor de principes, wellicht dat hier dan alleen nog wat 
  handreikingen worden gedaan m.b.t. de wijze waarop in de praktijk met de API Best Practices in de UGM's moet worden omgegaan.

> Een voorzet voor de API Best Practices wordt [hier](https://github.com/VNG-Realisatie/API-Kennisbank/blob/master/Analyse%20API%20Design/Analyse%20API%20Design.md) 
  gedaan.

#### Generieke methodes

##### Verwerking 'isEen' relaties

Het komt af en toe voor dat in een Informatiemodel een objectclass middels meerdere 'isEen' relaties verwijst naar andere objectclasses.
Het lijkt er dan op dat de objectclass meerdere supertypeclasses heeft. In de met deze relaties gekoppelde objectclasses zijn dan attributen aangebracht die specifiek 
zijn voor het betreffende type.
Binnen UGM zal je deze 'isEen' relaties waarschijnlijk willen oplossen. Dat kun je doen door de betreffende attributen op te nemen in de verwijzende entiteit en 
daarnaast een 'xxxType' attribuut op te nemen waarmee je bij de instantiërende resource kunt aangeven om wat voor type het gaat. Dat attribute kent dan als datatype een enumeratie.

##### Toekomstig in te vullen objecttypen

Bij het vervaardigen van een informatiemodel baseren we ons op de realiteit. Sterker nog, een informatiemodel is niet anders dan een model van de realiteit. De 
realiteit is echter complex en bij het modelleren simplificeer je de realiteit vooral kijkend naar wat je nodig hebt om de userstories in te kunnen vullen. Af en toe 
zal je daarbij een voorschot nemen op mogelijk in de toekomst in te vullen userstories met als gevolg dat er objectclasses in het informatiemodel worden opgenomen die
je (nog) niet nodig hebt.
In het UGM, waarin we alleen dat modelleren wat we voor de userstories technisch nodig hebben worden de entiteiten die relateren aan deze objectclasses dan ook 
verwijderd.

#### Yaml specifieke methodes

##### uuid en url attributen

Alle resources moeten m.b.v. een uuid op te vragen zijn en alle resources worden ook met een unieke url ontsloten. Om die reden wordt aan alle entiteiten in het UGM 
de attributen 'uuid' en 'url' toegevoegd. 

#### VerStUFfingsmethodes

> **Noot**: Dit hoofdstuk moet door Henri gevuld worden. Eigenlijk moeten we de term 'VerStUFfen' uitfaseren.

Hier komt een uitleg m.b.t. de overwegingen om objecttypen samen te voegen of plat te slaan in andere objecttypen, gegevensgroepen te koppelen en (technische) 
attributen toe te voegen.

#### VerStUFfingsmethodes domeinspecifiek UGM

In een domeinspecifiek SIM wordt (meestal) ergens een koppeling gemaakt met het RSGB of het RGBZ. Over het algemeen zal 1 of meer objecten uit het RSGB of het RGBZ 
ook voorkomen in het domeinspecifieke SIM. Eventueel ook met een aantal domeinspecifiek toegevoegde  attributen.

In het domeinspecifieke SIM wordt deze relatie gelegd door  een objecttype op te nemen met dezelfde naam als de naam die in het SIM RSGB of het SIM RGBZ wordt 
gehanteerd en deze als Stereotype "Proxy" op te nemen. In deze klasse worden de gewenste attribuutsoorten die reeds in het RSGB gedefinieerd zijn ook opgenomen, 
maar ook in dit geval met de stereotype "Proxy". Bij beide proxies (zowel de objecttypen als de attribuutsoorten) worden geen eigenschappen opgenomen en wordt voor 
het ophalen van deze eigenschappen een trace aangelegd tussen de "Proxy" klassen en het objecttype uit het RSGB dat als bron dient.  

Eventuele toe te voegen attribuutsoorten (die we in het RSGB dus nog niet kennen) worden in de Proxy-klasse opgenomen met het stereotype "Attribuutsoort".  Bij deze 
toegevoegde attribuutsoorten moeten wel alle eigenschappen worden opgenomen die nodig zijn om de attribuutsoort eenduidig te kunnen definiëren. 

Daarnaast kunnen in een koppelvlak-specifiek SIM objecttypen worden toegevoegd die onderling, (maar ook met de Proxy-klassen) gerelateerd kunnen zijn. Deze 
toegevoegde objecttypen hebben ook het stereotype objecttype.
Dat ziet er bijvoorbeeld als volgt uit. De beige objecttypen zijn domeinspecifiek en de blauwe objecttypen zijn onderdeel van het SIM RSGB.

![Domein specifiek SIM][Domein-specifiek-SIM]

Het bovenstaande is een voorbeeld van een Informatiemodel dat ten grondslag ligt aan het UitwisselingsGegevensModel (UGM) dat wordt opgesteld t.b.v. een koppelvlak. 
Bij het maken van een domeinspecifiek (of koppelvlakspecifiek) UGM wordt enerzijds hergebruik gemaakt van entiteittypen die al eerder gemodelleerd zijn en anderzijds 
worden er nieuwe entiteittypen geïntroduceerd naar aanleiding van nieuw in het domeinspecifieke informatiemodel gedefinieerde objecttypen.

Voor die objecttypen die  in het domeinspecifieke informatiemodel als proxy zijn opgenomen wordt gekeken naar het UGM waarin de betreffende objecttypen al eerder zijn 
vormgegeven tot entiteittype. Hierbij zijn "verStUFfingsregels" toegepast. De kans is zeer groot dat de overwegingen om objecttypen samen te voegen, gegevensgroepen 
te koppelen of (technische) attributen toe te voegen die eerder van toepassing waren ook bij het maken van het domeinspecifieke UGM van toepassing zullen zijn. 

Kort samengevat geldt dat voor elk Proxy-objecttype dat opgenomen is in het domeinspecifieke SIM het corresponderende entiteittype gekopieerd wordt  uit het 
"generieke" UGM. (Het UGM dat is afgeleid van het SIM waarnaar de Proxy verwijst). 
Vervolgens wordt dit gekopieerde entiteittype op maat gemaakt voor het domeinspecifieke UGM. Attributen worden verwijderd als deze niet voorkomen in het koppelvlak 
en attribuutsoorten die in een Proxy klasse zijn toegevoegd worden in het entiteittype toegevoegd als attribuut.

![Domein specifiek UGM][Domein-specifiek-UGM]

> **Noot**: Op de nieuwe entiteittypen die naar aanleiding van nieuw in het domeinspecifieke informatiemodel gedefinieerde objecttypen in het domeinspecifieke UGM 
  worden geïntroduceerd kan net zoals de entiteittypen in de "generieke" UGM's natuurlijk ook een verStUFfingsslag van toepassing zijn. Daarvoor gelden dezelfde 
  technieken als voor het verStUFfen van entiteittypen in de "generieke" UGM's (zie de voorgaande paragraaf).

## 4.4. Het opstellen van een koppelvlak

[**Terug naar top**](#4-de-nieuwe-werkwijze)


 In dit hoofdstuk beschrijven we hoe je tot de technische specificaties van een koppelvlak kunt komen. Althans wat betreft de StUF XML-Schema's en OAS3 specificatie. 
Een koppelvlakspecificatie bestaat immers uit meer dan alleen een van deze componenten. Denk onder andere aan de functionele documentatie maar ook aan een 'Getting 
started'.

Voor zowel StUF XML-Schema's als een OAS3 specificatie is het uitgangspunt dat er een valide UGM en dus ook een valide SIM voor het koppelvlak voor handen is. De 
paragrafen [Opstellen van een Koppelvlak-informatiemodel](...) en [opstellen van een koppelvlak-UitwisselingsGegevensModel](...) gaan daar dieper op in. De details 
over het modelleren van berichtspecificaties staan beschreven in paragraaf  433 opstellen van een koppelvlak-BerichtStructuurModel .

Voor het zover is moeten echter de onderstaande stappen genomen worden.

### 4.4.1. Wens voor een koppelvlak onderkennen

VNG Realisatie vult een rol in als het gaat om het in beeld krijgen van de behoefte aan koppelvlakken. Dat kan vanuit twee perspectieven. 

#### Architectuurperspectief

Vanuit een architectuur-benadering kan geconstateerd worden dat het voor de hand ligt om tussen twee referentiecomponenten een koppelvlak met een specifiek doel te 
definiëren. Volgend daarop zal altijd getoetst moeten worden of de behoefte aan deze koppelvlakspecificatie ook bestaat dan wel gemeenten ervan bewust moeten worden 
gemaakt wat de effecten zijn als een dergelijk koppelvlak wordt gedefinieerd. Uiteindelijk moet er bij de gemeenten draagvlak zijn voor een koppelvlak. 

#### Concrete behoefte

Vanuit de dagelijkse praktijk van gemeenten kan de behoefte aan een koppelvlak worden gedefinieerd. Hierbij kunnen concrete uitwisselingsproblemen of een concrete 
functionele (uitbreidings-)wens ten grondslag liggen. De hier gedefinieerde behoefte aan een koppelvlak zal altijd moeten worden afgebeeld op de architectuur. Welke 
referentiecomponenten spelen hier een rol, Is de behoefte wel een reëel koppelvlak-issue of wordt er een probleem opgelost dat is ontstaan omdat er niet onder 
architectuur is gewerkt etc....

#### Wettelijke eis

> **Noot**: Dit lijkt mij ook een perspectief dat benoemt moet worden. Wellicht kan dit ook beschouwd worden als een concrete behoefte maar die behoefte leeft 
  misschien heel ergens anders dan bij de gemeenten.

### 4.4.2. Keuze maken om het koppelvlak uit te gaan werken

Het uitwerken van een koppelvlak is in feite een investeringsbeslissing. Daarbij zal een afweging gemaakt moeten worden van de voor- en de nadelen vanuit het 
perspectief van de gemeenten. Daarnaast wordt in kaart gebracht welke resources er nodig zijn, hoe actueel het op te lossen probleem is en hoe groot de impact op het 
gemeentelijk applicatie-landschap zal zijn. 

> **Noot**: De investeringsbeslissing kan n.m.m. in het geval van een wettelijke eis mogelijk helemaal niet liggen bij de gemeenten. Ik kan me zelfs voorstellen dat 
  het budget door een andere partij ter beschikking wordt gesteld.

### 4.4.3. Werkgroep samenstellen

Werkgroepdeelnemers uitnodigen. Wens is altijd een goede gemeentelijke vertegenwoordiging, aangevuld met relevante leveranciers.
Er moeten op voorhand werkafspraken gemaakt worden over de volgende zaken :
* Voldoende beschikbare tijd voor werkgroepbijeenkomsten en het doen van uitwerkingen.
* Deelnemers zijn mede-eigenaar van het resultaat (dus geen aanpassingen/commentaar via de openbare consultaties.)
* Het doen van proefimplementaties binnen de projectperiode (project loopt door na de vaststelling of vaststelling pas na proefimplementatie. )

> **Noot**: Inmiddels werken we op een andere wijze. Werkgroepen zijn vervangen door communities waarin vertegenwoordigers van zowel gemeenten als leveranciers 
  kunnen deelnemen. De gebruikte tooling moet het werken in communities ondersteunen en om die reden wordt inmiddels gebruik gemaakt van zowel GitHub als GitLab. 
  Veelal wordt een agile werkwijze gehanteerd waarbij bij de opstart van het project voorzien is in de rollen benodigd voor de gekozen agile werkwijze. Zo is er 
  bij een scrum werkwijze bijv. voorzien in een Project Owner en een Scrum Master. Met het verschuiven van de traditionele keuze voor StUF als koppelvlak techniek 
  door REST API's zijn ook de op te leveren producten gewijzigd. Een belangrijke deliverable is voortaan de Referentie Implementatie. Tenslotte is ook de 
  kwaliteitscontrole en het goedkeuringsproces flink gewijzigd. De kwaliteit van de opgeleverde Referentie Implementatie en de OAS3 specificatie wordt gedurende 
  de ontwikkeling van de nieuwe standaarden gecontroleerd in een of meerdere API-Labs en de goedkeuring van deze producten is niet meer bij een Regiegroep belegd. 
  Het lijkt me daarom goed deze paragraaf te herschrijven en de titel te wijzigen. Wel moet er aandacht zijn voor die trajecten die nog wel de oude werkwijze 
  hanteren en die nog wel de oude producten opleveren.

### 4.4.4. Functionele wensen en eisen formuleren

Door de werkgroep zullen de functionele eisen en wensen ten aanzien van het koppelvlak gedefinieerd moeten worden. Hierbij dienen de volgende aspecten in acht 
genomen te worden :
* Welke gegevens spelen een rol binnen het koppelvlak /domein
* Welke van die gegevens maakt al onderdeel uit van een bestaand Informatiemodel (RSGB of RGBZ)
* Welk interoperabilitietsprobleem wordt met dit koppelvlak opgelost. 
* Uit welke berichten (berichtsoorten / content) bestaat het koppelvlak.
* Welke eisen worden er gesteld ten aanzien van de verwerking van deze berichten.

> **Noot**: In het kader van het werken met communities, het intensiever betrekken van gemeenten bij de ontwikkeling van koppelvlakken en een agile aanpak wordt 
  tegenwoordig vaak gestart met het definiëren van userstories. Dit zorgt er voor dat iedereen die dat wil zijn invloed kan pakken en de richting die de ontwikkeling 
  van een koppelvlak neemt kan beïnvloeden. De aanpak is immers transparanter omdat het verwerken van de userstories in alle openheid gebeurd.

### 4.4.5. Koppelvlak-informatiemodel opstellen 

Op basis van de functionele eisen en wensen of de userstories wordt geïnventariseerd welke informatie-objecttypen, -relatietypen en -attribuuttypen er voor het 
koppelvlak nodig zijn. Deze worden vervolgens vastgelegd in een Semantisch InformatieModel dat specifiek voor het koppelvlak in beeld brengt om welke informatie het 
gaat. 

Het opstellen van een verticaal informatiemodel wijkt in feite niet af van het opstellen van een horizontaal informatiemodel.
In principe kan een verticaal informatiemodel ook op zichzelf staan en geen relatie hebben met enig ander (horizontaal of verticaal) informatiemodel. wat het een 
verticaal informatiemodel maakt is dat haar toepassing alleen een specifiek koppelvlak betreft.

#### Relaties tussen horizontale en verticale modellen onderling m.b.v. Proxy-klassen.

In een verticaal informatiemodel is het mogelijk dat er "hergebruik" wordt gemaakt van objecttypen uit een horizontaal of ander verticaal informatiemodel. 
Dit wordt gedaan door in het informatiemodel een objecttype op te nemen met dezelfde naam als de naam in het gerelateerde informatiemodel en deze met de stereotype 
'objecttype_proxy' op te nemen. In deze klasse worden alleen de (in het gerelateerde informatiemodel gedefinieerde) attribuutsoorten opgenomen die gewenst zijn, maar 
met het stereotype 'Attribuutsoort_proxy'. Bij beide proxies (zowel de objecttypen als de attribuutsoorten) worden geen eigenschappen opgenomen en wordt voor het 
ophalen van deze eigenschappen een trace aangelegd tussen de "Proxy" componenten en de componenten in het gerelateerde informatiemodel dat als bron dient. Voor 
gegevensgroeptypes geldt hetzelfde alleen wordt daarvoor het stereotype 'Gegevensgroeptype_proxy' gebruikt.

Eventuele aan de proxy objecttypes en gegevensgroeptypes toe te voegen attribuutsoorten (die in het gerelateerde informatiemodel dus nog niet aanwezig zijn) worden 
in deze proxy-classes opgenomen met het stereotype 'Attribuutsoort'.  Bij deze toegevoegde attribuutsoorten moeten wel alle eigenschappen worden opgenomen die nodig 
zijn om de attribuutsoort eenduidig te definiëren. Aangezien deze attribuutsoorten geen basis hebben in een ander informatiemodel en dus eigenlijk zelf als bron 
fungeren moet er op dit soort attributen de tagged value 'Is afgeleid' gedefinieerd worden met de waarde 'Nee'.

Het onderstaande voorbeeld moet nog vervangen worden door een concreter praktijk-voorbeeld.

![Dom spec SIM][Dom-spec-SIM]

#### Opstellen van een domeinspecifiek informatiemodel (KV-SIM)

##### Toelichting

In een domeinspecifiek SIM wordt vrijwel altijd een koppeling gemaakt met een horizontaal Informatiemodel (bijv. RSGB of RGBZ). Over het algemeen zullen een aantal 
objecttypen uit die horizontale informatiemodellen ook voorkomen in het domeinspecifieke SIM. Het is mogelijk dat deze objecttypen worden aangevuld met een aantal 
domeinspecifieke  attribuutsoorten. Daarnaast zullen er ook domeinspecifieke objecttypen met hun attribuutsoorten opgenomen kunnen worden in een domeinspecifiek SIM. 

In het domeinspecifieke SIM wordt de relatie naar het horizontale model (supplier-model) gelegd door een objecttype op te nemen met dezelfde naam als de naam die in 
het horizontale model (bijv. het SIM RSGB of het SIM RGBZ) wordt gehanteerd. In deze klasse worden de gewenste attribuutsoorten die reeds in het horizontale 
informatiemodel gedefinieerd zijn ook opgenomen. Er worden tussen het domeinspecifieke informatiemodel en het horizontale informatiemodel traces aangelegd tussen de 
objecttypen en de attribuutsoorten. 

> **Vraag**: Is dit niet ook een situatie dat er proxy types gebruikt moeten worden?  

"Hiervoor wordt het traceability-script zonder transformatie" gebruikt.

> **Vraag**: Klopt dit wel?  

Eventuele toe te voegen attribuutsoorten (die we in het horizontale informatiemodel dus nog niet kennen) worden aan het objecttype toegevoegd met het stereotype 
'Attribuutsoort'.  Bij deze toegevoegde attribuutsoorten moeten alle eigenschappen worden opgenomen die nodig zijn om de attribuutsoort eenduidig te definiëren. 

Daarnaast kunnen in een koppelvlak-specifiek SIM objecttypen met hun relaties worden toegevoegd. Deze objecttypen kunnen onderling ook nog gerelateerd zijn. Deze 
toegevoegde objecttypen hebben ook het stereotype 'Objecttype'.

##### Praktische werkwijze

Het maken van een informatiemodel is een denkproces dat gaandeweg en met voortschrijdend inzicht doorlopen wordt. Daarover gaan we hier inhoudelijk niets zeggen. 
Uiteindelijk wordt het KV-informatiemodel vastgelegd als UML-model in Enterprise Architect. Daarvoor wordt de volgens werkwijze gehanteerd:

* Maak een package aan onder het project KING: SIM;
* Geef deze package de naam van het koppelvlak (SIM [_Koppelvlaknaam_]);
* Geef de package het stereotype 'basismodel';
* Geef een korte beschrijving van het SIM in het notitieveld;
* Voer de volgende Tagged Values op bij de package: 
  * 'Is afgeleid' (waarde = 'Ja');
  * 'release' (formaat = 'jjjjmmdd')
  * 'supplier-name' (de naam van het model waarvan dit informatiemodel is afgeleid. Dit kunnen er meerdere zijn en in dat geval wordt elke waarde gescheiden met een 
    ';')
  * 'supplier-project' (de naam van het project waar het supplier-model onderdeel van uitmaakt. Ook dit kunnen er meerdere zijn, en ook hier worden deze dan 
    gescheiden met een ';'. Let er op dat de volgorde van de waarden overeenkomt met die in de tagged-value 'supplier-name'). 
  * 'supplier-release' (de release van het supplier-model. Hier gelden dezelfde voorwaarden als bij de voorgaande 2 tagged values).

> **Noot**: Ik betwijfel of de tagged value 'Is afgeleid' daar wel nodig is.  

* Maak binnen het zojuist aangemaakte package een nieuwe package aan met de naam 'Model';
* Geef deze nieuwe package het stereotype 'Domein';
* Maak binnen het package 'Model' de volgende packages aan:
  * 'Objecttype';
  * 'Relatieklasse';
  * 'Gegevensgroeptype';
  * 'Referentielijsten';
  * 'Complex datatype';
  * 'Enumeratiesoort';
* Maak naast het package 'Model' een package 'Diagram' aan;
* Creëer een eerste diagram in het 'Diagram' package. Naamgeving is voor nu nog niet van belang die kun je later bijstellen;
* Doe voor elk supplier model het volgende:
  * Maak binnen het zojuist aangemaakte package een nieuwe package aan met een naam die refereert aan het supplier model;
  * Geef deze nieuwe package het stereotype 'Prullenbak';
  * Kopieer het volledige supplier-model (d.m.v. 'Full Structure for Duplication') naar het nieuwe package;
  * Verwijder zo nodig de versie control van het gekopieerde package (zie  5.2 Technieken en handigheidjess#Verwijderen-van-versie-control-op-een-package );
  * Voer het script 'Set Traceability without Transformation' uit op het package en koppel aan het package waaruit het zojuist gekopieerd is.
* Kopieer nu uit de 'Prullebak' packages de objecttypes die je nodig hebt voor je koppevlak SIM;
* Plaats de gekopieerde objecttypes in het eerder vervaardigde diagram. Daarmee heb je een overzicht en kun je de andere benodigde componenten bepalen;
* Verwijder (indien je dat in dit stadium al kunt bepalen) alle niet benodigde attribuutsoorten uit de zojuist gekopieerde objecttypes;
* Kopieer nu uit de 'Prullebak' packages de andere componenten die je nodig hebt binnen de eerder gekopieerde objecttypes. Dus alle 'relatieklasses', 
  'gegevensgroeptypes', 'referentielijsten', 'complex datatypes' en 'enumeratiesoorten';
* Verwijder (indien je dat in dit stadium al kunt bepalen) alle niet benodigde attribuutsoorten uit de zojuist gekopieerde objecttypes;
* Herhaal bovenstaande 2 stappen totdat je alle benodigde componenten uit de supplier modellen compleet hebt;
* In principe kunnen de 'Prullenbak' packages nu verwijderd worden. Met de objecttypen die dan verwijderd worden worden ook de relaties die de verplaatste objecttypes 
  daarmee hadden verwijderd. Hetzelfde geldt voor de relatieclasses en die van toepassing waren op de relaties tussen de verplaatste objecttypes. Verwijderen kan 
  echter ook uitgesteld worden tot een later moment indien je nog niet zeker bent van de in het koppelvlak benodigde componenten uit de supplier modellen;
* Nu kun je de stereotypes van alle 'objecttypes', 'gegevensgroeptypes' en 'attribuutsoorten' wijzigen naar 'Objecttype_proxy', resp. 'Gegevensgroeptype_proxy' en 
  'Attribuutsoort_proxy';
* Tenslotte kun je nu de andere voor het koppelvlak SIM benodigde objecttypes, gegevensgroeptypes, relatieklasses, referentielijsten, complex datatypes, 
  enumeratiesoorten, attribuutsoorten, referentie elementen en enumeraties toevoegen. Let er daarbij op dat deze componenten de tagged value 'Is afgeleid' met de waarde 'Nee' moeten krijgen;

> **Noot**: Zonodig moet de bovenstaande procedure uitgebreid worden.  

> **Noot**: Onderstaande moet n.m.m. opgenomen worden in paragraaf 4.3.2 over het opstellen van een Koppelvlak UitwisselingsGegevensModel.

Met bovenstaande procedure creëren we een Informatiemodel dat ten grondslag zal liggen aan het UitwisselingsGegevensModel (UGM) dat later opgesteld wordt. Bij het 
maken van een domeinspecifiek (of koppelvlakspecifiek) UMG wordt enerzijds hergebruik gemaakt van entiteittypen die al eerder gemodelleerd zijn en anderzijds worden 
er nieuwe entiteittypen geïntroduceerd naar aanleiding van nieuw gedefinieerde objecttypen. 

Voor die objecttypen die als proxy opgenomen zijn in het koppelvlak-specifieke informatiemodel wordt gekeken naar het UGM waarin de betreffende objecttypen al eerder 
zijn vormgegeven tot entiteittype. Hierbij zijn "verstuffingsregels" toegepast. De kans is zeer groot dat de overwegingen om objecttypen samen te voegen, 
gegevensgroepen te koppelen of (technische) attributen toe te voegen die eerder van toepassing waren ook bij het maken van het koppelvlak-specifieke UGM van 
toepassing zullen zijn. 

Kort samengevat geldt dat voor elk Proxy-objecttype dat opgenomen is in het koppelvlak-specifieke SIM het corresponderende entiteittype wordt gekopieerd uit het 
"generieke" UGM. (Het UGM dat is afgeleid van het SIM waarnaar de Proxy verwijst). 
Vervolgens wordt dit gekopieerde entiteittype op maat gemaakt voor het koppelvlak-specifieke UGM. Attributen worden verwijderd als deze niet voorkomen in het 
koppelvlak en attribuutsoorten die in een Proxy klasse zijn toegevoegd worden in het entiteittype toegevoegd als attribuut. 

![Dom spec UG<][Dom-spec-UGM]

### 4.4.6. Koppelvlak-uitwisselingsgegevensmodel opstellen

Op basis van het koppelvlak Semantisch InformatieModel en eventueel te hergebruiken deel of delen van horizontale Uitwisselingsgegevensmodellen wordt een een 
koppelvlak UitwisselingsGegevensModel opgesteld. 

Het UitwisselingsGegevensModel (UWM) van een koppelvlak omvat alle entiteittypen, elementen en relaties die binnen de berichten van het koppelvlak van belang zijn en
gebruikt worden. 
Dit uitwisselingsmodel is enerzijds een uitwerking van het Semantisch InformatieModel (SIM) van een koppelvlak (Veritcaal informatiemodel, zie ook  431 Opstellen van 
een Koppelvlak-informatiemodel ) en waar van toepassing een selectie uit een horizontaal UGM. 

In de praktijk zal een verticaal UGM gebaseerd worden op een kopie van het horizontale UGM waarop het gebaseerd is. Voor een koppelvlak dat voor het grootste deel 
(zo niet alle) gegevens bevat die onderdeel uitmaken van het RSGB betekent dit dat er gewerkt wordt op basis van een kopie van het horizontale UGM BG. In dit 
horizontale UGM zijn namelijk alle verstuffings-regels toegepast. Objecttypen zijn samengevoegd vanuit toepassings-perspectief en relaties zijn, waar nodig,  
specifieker benoemd dan in het SIM. Verder zijn datatypen omgezet naar een formeel (te interpreteren) patroon. 

Al deze bovenstaande kennis en het daadwerkelijk doorvoeren daarvan in het UGM wordt hergebruikt door het package van het horizontale UGM te kopiëren.  Dat is dan 
ook de eerste slag naar een verticaal UGM.
Vervolgens moeten de properties van het nieuwe package aangepast worden. Geef het een nieuwe naam, een nieuwe alias (de namespace uri van het nieuwe koppelvlak), 
wijzig de author en indien van toepassing het versienummer en de phase.

Indien op dit moment al duidelijk is of en zo ja welke objecten, attributen en relaties je niet nodig hebt dan kun je die nu al gaan verwijderen.
Dit mag ook nog op een later moment maar hoe kleiner het model hoe sneller de volgende stap zal verlopen.

De objecten, attributen en associations van het nieuwe model tracen nog naar het SIM waar het originele UGM van was afgeleid.
Ze moeten nu echter gaan verwijzen naar de gerelateerde objecten, attributen en relaties in het originele UGM.
Hiervoor dien je het script 'Set traceability with transformations' uit te voeren op het nieuwe package (zie de handreikingen voor een beschrijving hoe je dit kunt 
doen).

Vervolgens kun je op basis van het verticale SIM het verticale UGM aanpassen. Dat wil zeggen dat de volgende acties moeten worden ondernomen:
* Alle objecten uit het verticale SIM moeten naar het nieuwe verticale UGM worden gekopieerd;
* De stereotypes van alle objecten, attributen en relaties moeten worden omgezet naar de UGM variant daarvan;
* Eventueel kan ook op dit UGM een verStUFfing op de nieuwe objecten, attributen en relaties worden toegepast (zie ook  421 Technische en implementatie-overwegingen;
* Voor alle nieuwe objecten en bij die objecten horende attributen en relaties moeten de traces naar het oorspronkelijke verticale SIM worden geleid.

> **Noot** Is er voor het hierboven beschreven proces een script die een Copy/Paste uitvoert, de omzetting doet van de stereotypes en de traces plaatst? Of moet dit 
  in dit geval handmatig gebeuren?

Vuistregels :
* De relatie tussen een objectype of gegevensgroeptype enerzijds en een gegevensgroeptype anderzijds wordt altijd voorzien van een naam.
* Voor BSM : In een vraagbericht hebben de relaties naar de fundamentele entiteit een vaste naam en van elke naam mag er maar 1 voorkomen. De namen zijn 'gelijk', 
  'vanaf', 'totEnMet', 'scope' en 'start'. 

> **Noot** De eerste vuistregel is ook van toepassing op een horizontaal UGM en moet dus ook in de beschrijving terugkomen van het opstellen van zo'n UGM. De tweede 
  vuistregel is voor het opstellen van een BSM en moet daarheen verhuizen zodra we die gaan opstellen. We moeten trouwens checken of deze vuistregel ook gevalideerd 
  wordt.
 
#### Het vormgeven van een choice-constructie in UML middels een XOR

> **Noot** Volgens mij is deze paragraaf nog niet van toepassing.

Een choice wordt in UML vormgegeven door een XOR op relaties. Dat betekent dat een choice tussen twee entiteittypen vormgegeven wordt door een XOR op de relaties van 
het basis entiteittype met de twee gerelateerde entitiettypen. Een choice tussen twee gegevensgroeptype wordt vormgegeven door een XOR op de relaties tussen het 
basisentiteittype of gegevensgroeptype enerzijds en de gerelateerde gegevensgroeptypen anderzijds.  Als er een choice gemaakt moet worden tussen twee enkelvoudige 
attributen dan wordt dit gerealiseerd door deze twee attributen ieder in een gegevensgroeptype te plaatsen en vervolgens een XOR te maken op de relaties met die 
gegevensgroeptyepen. Mogelijk vinden we in de toekomst een betere oplossing,  maar voor nu wordt deze constructie gehanteerd.

#### Speciale situaties

Bij het definieren van een UGM model kunnen zich speciale situaties voordoen. We hebben deze situaties elders beschreven. Hieronder een overzicht met een link naar 
de betreffende locatie:

* Meerdere entiteiten gebaseerd op dezelfde entiteittypen: Zie  6 Wetenswaardigheden en specials#Meerdere-entiteiten-gebaseerd-op-dezelfde-entiteittypen 

### 4.4.7. Koppelvlak-berichtstructuurmodel opstellen

Op basis van het koppelvlak UitwisselingsGegevensModel wordt een koppelvlak BerichtStructuurModel opgesteld. Hierbij spelen ook eventueel opgestelde userstories weer 
een belangrijke bron van informatie.

#### Koppelvlak aanmaken.

* Package aanmaken onder het project KING: BSM met de naam van het koppelvlak. (De naamgevingsconventie is: BSM KV Naam koppelvlak)
* In properties het Stereotype “koppelvlak” geven.
* Het veld 'Alias'  vullen met de namespace van het koppelvlak opnemen(bv /demo.kinggemeenten.nl). Dit is alleen van belang bij het genereren van StUF koppelvlakken.
* Het veld 'Version' vullen met het semantic versienummer van een API koppelvlak of het 4-cijferig versienummer van een StUF koppelvlak.
* Het veld 'Phase' vullen met een van de volgende waarden ...... <-- opzoeken.
* De volgende tagged values moeten opgenomen worden :
  1. 'derived' : heeft de waarde 'yes' als er afleiding van een ander model plaatsvindt (en dat is vrijwel altijd het geval). <-- Is dit echt nodig?
  2. 'release' : de datum waarop begonnen is met de release in het format yyyymmdd. Dit moet altijd groter zijn dan de release van het supplier-model.
  3. 'supplier-name' : de naam van het UGM waar het koppelvlak op is gebaseerd (bv. UGM KV Naam koppelvlak). Alle traces vanuit het BSM lopen naar dit UGM.
  4. 'supplier-project' : heeft in dit geval altijd de waarde 'UGM' ( het project waar het supplier-model is ondergebracht).
  5. 'supplier-release' :  de datum van de release in het format yyyymmdd van het supplier-model
  6. 'verkorte alias' : alias waarmee de koppelvlak-namespace wordt geïdentificeerd in de StUF bericht schema's (alleen bij StUF koppelvlakken)
  7. 'beheerder_email': e-Mailadres waarop jij als beheerder bereikbaar bent.
  8. 'koppelvlak-naam': naam van het koppelvlak.
  9. 'project_url': url van het GitHub project waarbinnen de API standaard wordt ontwikkeld. (Alleen bij API koppelvlakken)
  10. 'serialisatie': in het geval van een API koppelvlak moet aangegeven worden of het als plain 'JSON' moet worden gegenereerd of als 'Hal+JSON'. (Alleen bij API 
      koppelvlakken)

* De volgende tagged values mogen opgenomen worden:
  1. 'toelichting opnemen vanaf' : ................
  2. 'Versienummer AAA nnnnnn' : Voor elk supplier model 1. Hier kan het betreffende versienummer van dat model opgenomen worden. 'AAA' heeft de waarde 'SIM' of 'UGM'. 
     'nnnnnn' bevat de naam van het betreffende model.

* Neem het interne package "Berichtstructuren" op.
* Neem het interne package "Generieke Datatypen" op. 

Voor het supplier-model geldt dat dit in een imvertor-run gedraaid moet zijn voordat het koppelvlak-model gedraaid wordt. Anders kent imvertor het supplier-model niet 
en kan er geen derivation plaatsvinden.

#### Bericht aanmaken (dit zullen er over het algemeen meerdere per koppelvlak zijn)

##### Berichtpackage

* Bericht-package aanmaken onder de koppelvlak-package.
* In de properties het stereotype “bericht” toevoegen.
* Naam van de namespace voor het koppelvlak toevoegen in de alias.
* Properties opslaan. Daarna tonen dat de tab MBG is toegevoegd aan de properties. 
* Tab “MBG” tonen. Toelichten van de eigenschappen van het bericht als documentatie.

##### Berichtcontent

* Schema-composer starten (TOOLS > Schema Composer)
* New > Schema >
* Naam bericht invoeren.
* Schema-set : Selecteer ECDM Message Composer
* Selecteer de package waarin het bericht wordt opgeslagen (Package dat zojuist zoals hierboven beschreven is aangemaakt. )
* Haal de fundamentele entiteit van het bericht op uit het UGM.
* Selecteer de gewenste attributen, gegevensgroepen, enumeraties en relaties toe.
  (De werking van de Schema-composer vereist wat uitleg)

##### Complexe content (modelleerprincipes)

###### Recursieve relaties

####### Bij STUF
  
Voor de berichten waarbij er vanuit een (fundamentele) entiteit een relatie naar zichzelf is gelegd is het van belang dat er een aangepaste entiteit wordt aangemaakt. 
Als voorbeeld de natuurlijk Persoon (NPS) die de recursieve relatie "heeftAlsKind" kent. 
Er wordt een NPS-kind (naamgeving is nog niet besproken en vastgesteld) of een NPS-kerngegevens gemaakt op basis van de NPS-entiteit die al in het bericht zit.
* Kopieer de NPS-entiteit
* Hernoem de kopie naar NPS-kind (Met deze twee acties blijven de traces op de attributen behouden naar de corresponderende entiteit uit het UGM.)
* Herstel de trace op de entiteit.
* Herhaal deze actie voor alle gerelateerde gegevensgroepen en entiteiten.
* Leg handmatig de relatie "heeftAlsKind" om van recursief naar een relatie tussen NPS en NPS-kind.
* Leg handmatig de composite-relaties met de gegevensgroepen aan. 

####### Bij REST/JSON
Voor een recursieve relatie wordt net als bij StUF koppelvlakken een aangepaste entiteit aangemaakt. Uitgaande van een voorbeeld waarbij 'Persoon' entiteit een link 
naar zichzelf heeft wordt het volgende gedaan:
* Kopieer de 'Persoon' entiteit;
* Hernoem deze naar 'Persoon_lnk';
* Herstel de trace op de entiteit;
* Verwijder evt. attributen indien je in het yaml bestand alleen een link naar de resource wil opnemen;
* Verwijder de betreffende relatie op het '_lnk' object;
* Verwijder ook evt. andere relaties indien in het yaml bestand alleen een link naar de resource wil opnemen.
(Wat moet je doen als je het object in zijn geheel op wil nemen? Moeten dan de links blijven staan?)
* Plaats het '_lnk' object in het diagram waarin de entiteit met de recursieve link voorkomt;
* Verleg de target van de recursieve link naar het geplaatste '_lnk' object.

###### Vraagberichten

Bij het modelleren van vraag antwoord combinatie (lv/la) dient de "start"-relatie uit de lv altijd naar dezelfde klasse te  verwijzen als de "object"- relatie uit 
het la-bericht. Gelijk, vanaf en totEnMet verwijzen altijd naar een ander complextype dan de Start. Voor scope loopt de discussie nog of deze naar hetzelfde 
complexType als antwoord mag verwijzen.  

###### Complextypes

Voor elke entiteitklasse, gegevensgroeklasse en elke relatie wordt per bericht slechts 1 complextype aangemaakt.
Uitzondering daarop zijn de historieFormeel, en historieFormeelRelatie historieMaterieel en de kerngegevens bij de gerelateerde.

#### *Genereer de bericht-content

Selecteer de knop "Generate"

#### Regels en afspraken bij het opstellen van een BSM.

+
*_Johan : Tot hier gekomen.... Rest is under construction*_+

- Orden de diagram

##### Berichttype

Generiek berichttype koppelen aan de content

Creëer een package met de naam van het bericht.
Geef deze package het gewenste bericht type. Keuze uit :
* Antwoordberichttype (La)
* Generiek Berichttype
* Kennisgevingberichttype(Lk)
* Synchronisatieberichttype (Sa, Sh)
* Vraagberichttype (Lv)
* Vrij berichttype (Di, Du)
Selecteer uit de interne package "berichtstructuren" de interface die correspondeert met het gewenste generieke bericht. 
Leg een


*Specifiek bericht (vrij bericht of een specifiek bericht o.b.v. generieke structuur) maken en koppelen aan de content*



*Genereer de bericht-content (knop "Generate")
- Orden de diagram
- Voeg berichttype toe 
- Pas tagged values aan waar nodig, voeg berichtcode toe waar nodig.
- Voeg de Entiteitrelatie toe* 

##### Complexere berichten

[PackageControlOptions]: https://kinggemeenten.plan.io/attachments/download/161704
[Domein-specifiek-SIM]: https://kinggemeenten.plan.io/attachments/download/159542/Dom-spec%20SIM.JPG
[Domein-specifiek-UGM]: https://kinggemeenten.plan.io/attachments/download/159479/Dom-spec%20UMG.JPG
[Dom-spec-SIM]" https://kinggemeenten.plan.io/attachments/download/159542/Dom-spec%20SIM.JPG
[Dom-spec-UGM]: https://kinggemeenten.plan.io/attachments/download/159479/Dom-spec%20UMG.JPG
