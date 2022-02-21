---
layout: page-with-side-nav
title: Tagged values
---
# Tagged Values

[**7.1. Tagged values voor de SIM (Semantische Informatie Modellen)**](#71-tagged-values-voor-de-sim-semantische-informatie-modellen)

[**7.3. Tagged values voor de BSM (Bericht Structuur Modellen)**](#72-tagged-values-voor-de-ugm-uitwisselingsgegevensmodel)

[**7.3. Tagged values voor de BSM (Bericht Structuur Modellen)**](#73-tagged-values-voor-de-bsm-bericht-structuur-modellen)

M.b.v. tagged values (TV's) kan aan constructies in UML extra semantiek meegegeven worden. De aanwezigheid van TV's kan m.b.v. metamodellen gefaciliteerd of m.b.v. 
Imvertor afgedwongen worden. In de volgende tabel staan TV's die noch gefaciliteerd noch afgedwongen worden. Daarnaast hebben ze ook geen functie voor |mvertor. Het is echter de afspraak dat we onze modellen er van voorzien ter documentatie.

| Tagged value naam | Waar| Verplicht (in) | Beschrijving | Mogelijke waarden | Afleiding mogelijk |
| --- | --- | --- | --- | --- | --- |
| Versienummer yyy xxxx | Packages | Nee | Versienummer van een suppliermodel. 'xxxx' komt dan overeen met een van de waarden genoemd in de TV 'Supplier-name'. De waarde van deze TV zelf komt overeen met de EA property 'Version' van het bewuste suppliermodel. Deze TV is strikt informatief. | bijv. '02.02.00' | Nee |

## 7.1. Tagged values voor de SIM (Semantische Informatie Modellen)

[**Terug naar top**](#7-tagged-values)

| Tagged value naam | Waar | Verplicht (in) | Beschrijving | Mogelijke waarden _(in vet de defaultwaarde)_ | Afleiding mogelijk |
| --- | --- | --- | --- | --- | --- |
| 'Aanduiding strijdigheid/nietigheid' | Attribuutsoort, Gegevensgroeptype, Relatiesoort | Ja | De aanduiding of te bevragen is dat de attribuutwaarde strijdig met de openbare orde dan wel nietig is. | | Ja |
| 'Afkorting' | Basismodel Basismodel, Toepassing, Domein, View | Nee | Afkorting van dit model. Deze afkorting wordt o.a. gebruikt waar informatie over het model wordt gepubliceerd. | | Ja |
| 'Alternatieve naam' 'Naam' | Objecttype, Attribuutsoort, Relatiesoort, Gegevensgroeptype, Referentielijst, Codelist Codelijst, Referentie element, Union Keuze, Gestructureerd datatype, Externe koppeling, Enumeratie | Nee | De naam in natuurlijke of formele taal; afhankelijk van gekozen aanpak. Een alternatieve naam. | | Ja |
| 'Beheerder' | Extern | Nee | Naam van de beheerder van het model. | | Ja |
| 'Data locatie' | Extern, View | View | De locatie waar informatie over de gegevens van een construct te vinden zijn. Wanneer het een external of view package betreft: De verwijzing naar de locatie van het bijbehorende informatiemodel waar dit package een representatie van is. In alle andere gevallen moet het een waardenlijst betreffen. Het gaat dan om de verwijzing naar de plek waar de waarden beschikbaar worden gesteld. De verwijzing heeft de vorm van een URI conform een gekozen URI strategie. | | Ja |
| 'Datum opname' | Objecttype, Attribuutsoort, Gegevensgroeptype, Relatiesoort, Referentielijst, Referentie element, Union Keuze, Gestructureerd datatype, Externe koppeling | Ja | **Wie kan hier een definitie van geven ?** | | Ja |
| 'Definitie' | Objecttype, Attribuutsoort, Relatiesoort, Gegevensgroeptype, Relatieklasse, Referentielijst, Referentie element, Enumeratie, Codelist Codelijst, Primitief datatype Primitief datatype, Gestructureerd datatype, Union Keuze, Data element, Union element Datatype, Enumeratiewaarde, Extern, View | Objecttype, Attribuutsoort, Relatiesoort, Relatieklasse, Referentielijst, Referentie element, Enumeratie, Codelist Codelijst, Primitief datatype Primitief datatype, Gestructureerd datatype, Union Keuze, | De beschrijving van de betekenis van de construct zoals gespecificeerd in de catalogus van de desbetreffende (basis)registratie of informatiemodel. | | Ja |
| 'Eigenaar' | Objecttype, Attribuutsoort, Gegevensgroeptype | Nee | *Wie kan hier een definitie van geven ?* | | Ja |
| 'Groepnaam' | Tekentechnisch | Nee | **Wie kan hier een definitie van geven ?** | | Ja |
| 'Herkomst' | Objecttype, Primitief datatype Primitief datatype, Gestructureerd datatype, Attribuutsoort, Relatiesoort, Gegevensgroeptype, Referentielijst, Union Keuze, Union element Datatype | Objecttype, Primitief datatype Primitief datatype, Gestructureerd datatype, Attribuutsoort, Relatiesoort, Referentielijst, Union Keuze, Union element Datatype | De basisregistratie in wiens catalogus het objecttype is gespecificeerd (oftewel de basisregistratie waar het objecttype deel van uitmaakt). Deze specificatie is toegevoegd omdat het wel duidelijk moet zijn in welke (basis)registratie of informatiemodel het objecttype voorkomt (indien van toepassing). | | Ja |
| 'Herkomst definitie' | Objecttype, Attribuutsoort, Gegevensgroeptype, Relatiesoort | Objecttype, Attribuutsoort, Relatiesoort | De basisregistratie of het informatiemodel waaruit de definitie is overgenomen dan wel een aanduiding die aangeeft uit welke bronnen de defintie is samengesteld. | | Ja |
| 'Imvertor' | Basismodel Basismodel, Toepassing | Nee | **Wie kan hier een definitie van geven ?** | | Nee |
| 'Indicatie authentiek' | Attribuutsoort, Gegevensgroeptype, Relatiesoort | Ja | Aanduiding of het een authentiek gegeven (attribuutsoort) betreft. | | Ja |
| 'Indicatie formele historie' | Attribuutsoort, Gegevensgroeptype, Relatiesoort | Ja | Indicatie of de formele historie van de attribuutsoort te bevragen is. Formele historie geeft aan wanneer in de administratie een verandering is verwerkt van de attribuutwaarde (wanneer was de verandering bekend en is deze verwerkt). | 'Ja', *'Nee'*, 'Zie groep' | Ja |
| 'Indicatie in onderzoek' | Attribuutsoort, Gegevensgroeptype, Relatiesoort | Ja | De indicatie of te bevragen is dat er twijfel is of is geweest aan de juistheid van de attribuutwaarde en dat een onderzoek wordt of is uitgevoerd naar de juistheid van de attribuutwaarde. | 'Ja', *'Nee'*, 'Zie groep' | Ja |
| 'Indicatie materiÃ«le historie' | Attribuutsoort, Gegevensgroeptype, Relatiesoort | Ja | Indicatie of de materiÃ«le historie van de attribuutsoort te bevragen is. MateriÃ«le historie geeft aan wanneer een verandering is opgetreden in de werkelijkheid die heeft geleid tot veranderjng van de attribuutwaarde. | 'Ja', *'Nee'*, 'Zie groep' | Ja |
| 'Intern project' | Intern | Ja | **Wie kan hier een definitie van geven ?** | | Nee |
| 'Interne naam' | Intern | Ja | **Wie kan hier een definitie van geven ?** | | Nee |
| 'Interne release' | Intern | Ja | **Wie kan hier een definitie van geven ?** | | Nee |
| 'Is afgeleid' | Project, Basismodel Basismodel, Toepassing, Domein, Extern, Intern, Objecttype, Relatiesoort, Data element, Attribuutsoort, Gegevensgroep, Referentielijst, Referentie element, Union Keuze, Union element Datatype, Enumeratie, Enumeratiewaarde, Gegevensgroeptype, Relatieklasse, Gestructureerd datatype, Primitief datatype Primitief datatype, Interface | Nee | Deze constructie is al dan niet afgeleid van een "supplier model". Wanneer je niks opgeeft wordt afleiding vastgesteld op basis van het package waarin het voorkomt. | 'Nee', 'Ja', *'Zie package'* | Nee |
| 'Is includeerbaar' | Product | Nee | Deze constructie kan via xi:include worden geincludeerd in het document. De equivalente constructie in het XML schema, of constructies daarbinnen, krijgt hierdoor dan een optioneel attribuut xml:base bijgevoegd. | 'Ja', *'Nee'* | JaJa |
| 'Kwaliteit' 'Kwaliteitsbegrip' | Objecttype | Nee | *Wie kan hier een definitie van geven ?* | | Ja |
| 'Mogelijk geen waarde' | Attribuutsoort, Gegevensgroeptype, Relatiesoort | Nee | Indicatie waarmee wordt aangegeven dat het gegeven ook geen waarde kan hebben. | 'Ja', *'Nee'* | Ja |
| 'Niveau' | Basismodel Basismodel | Nee | Het niveau is een waarde uit een beperkte set: "algemeen" betekent dat het model een fundament is van een ander model en moet worden opgenomen. Het modelleert generieke constructies die deel uitmaken van de echte wereld. Dit omvat meestal abstracte object typen. Het kan andere constructen bevatten. "specifiek" betekent dat het model een bepaald domein beschrijft of een samenhangend deel ervan . | 'generiek', *'specifiek'* | Nee |
| 'Patroon' | Attribuutsoort, Referentie element, Primitief datatype Primitief datatype, Gestructureerd datatype, Data element, Union element Datatype | Nee | Beschrijving van het gegevenspatroon van dit element. Dit kan de basis zijn voor een reguliere expressie. | | Ja |
| 'Populatie' | Objecttype | Nee | *Wie kan hier een definitie van geven ?* | | Ja |
| 'Positie' | Domein, Extern, Intern, Objecttype, Relatiesoort, Data element, Attribuutsoort, Referentielijst, Referentie element, Union Keuze, Union element Datatype, Enumeratie, Enumeratiewaarde, Relatieklasse, Gestructureerd datatype, Primitief datatype Primitief datatype, Interface | Nee | De positie van de construct binnen producten waarin deze opeenvolging een rol speelt. | | Ja |
| 'Ref-release' | Domein, View, Extern | Nee | **Wie kan hier een definitie van geven ?** | | Nee |
| 'Ref-version' | Domein, View, Extern | Nee | **Wie kan hier een definitie van geven ?** | | Nee |
| 'Regels' | Attribuutsoort, Gegevensgroeptype, Relatiesoort | Nee | Optionaliteitsregels of waardebeperkende regels. | | Ja |
| 'Release' | Basismodel Basismodel, Toepassing, Domein, View, Extern, Intern | Basismodel Basismodel, Toepassing, Domein, View, Intern | Dit bevat de releasedatum in het format yyyymmdd . De releasedatum wordt mede gebruikt om een model, koppelvlak of bericht uniek te identificeren in Imvertor. | Bijv. '20170901' | Nee |
| 'Supplier-name' | Basismodel Basismodel, Toepassing | Toepassing | Dit bevat de naam van het suppliermodel waarvan een model hergebruik maakt. Er zijn meerdere waardes mogelijk, gescheiden door een ; (puntkomma) Volgorde moet corresponderen met die in Supplier-project en Supplier-release. Alleen opnemen wanneer van afleiding sprake is. | Bijv. 'SIM;SIM' | Nee |
| 'Supplier-package-name' | Domein, View | Nee | De naam van de supplier (domein of view) package. Deze naam wordt opgegeven als deze niet gelijk is aan de naam van het package waar de tagged value op geplaatst is. | | Nee |
| 'Supplier-project' | Basismodel Basismodel, Toepassing | Toepassing | Dit bevat de naam van project waarbinnen het suppliermodel waarvan een model hergebruik maakt is opgenomen. Er zijn meerdere waardes mogelijk, gescheiden door een ; (puntkomma) . Volgorde moet corresponderen met die in Supplier-name en Supplier-release. Alleen opnemen wanneer van afleiding sprake is. | Bijv. 'RSGB;IMztc' | Nee |
| 'Supplier-release' | Basismodel Basismodel, Toepassing | Toepassing | Dit bevat de releasedatum in het format yyyymmdd van het suppliermodel waarvan een model hergebruik maakt. Er zijn meerdere waardes mogelijk, gescheiden door een ; (puntkomma) . Volgorde moet corresponderen met die in supplier-name en supplier-project. Alleen opnemen wanneer van afleiding sprake is. | Bijv. '20170901;20170801' | Nee |
| 'Toelichting' 'Omschrijving' | Objecttype, Attribuutsoort, Gegevensgroeptype, Relatiesoort, Referentielijst, Referentie element | Nee | Aanvullende beschrijving van het construct met de bedoeling dat te verduidelijken. | | Ja |
| 'Versie ID' | Basismodel Basismodel, Toepassing, Domein, Extern, View | Nee | De identificatie van de versie/revisie van dit model of model-element in het gehanteerde versiebeheersysteem. | | Nee |
| 'Web locatie' | Basismodel Basismodel, Toepassing, Extern, View, Domein | Nee | **Wie kan hier een definitie van geven ?** | | Ja |

## 7.2. Tagged values voor de UGM (UitwisselingsGegevensModel)

[**Terug naar top**](#7-tagged-values)

| Tagged value naam | Waar | Verplicht (in) | Beschrijving | Mogelijke waarden _(in vet de defaultwaarde)_ | Afleiding mogelijk |
| --- | --- | --- | --- | --- | --- |
| 'Afkorting' | Basismodel, Toepassing, Domein, View | Nee | Afkorting van dit model. Deze afkorting wordt o.a. gebruikt waar informatie over het model wordt gepubliceerd. | | Ja |
| 'Beheerder' | Extern | Nee | Naam van de beheerder van het model. | | Ja |
| 'Data locatie' | Extern, View | View | De locatie waar informatie over de gegevens van een construct te vinden zijn. Wanneer het een external of view package betreft: De verwijzing naar de locatie van het bijbehorende informatiemodel waar dit package een representatie van is. In alle andere gevallen moet het een waardenlijst betreffen. Het gaat dan om de verwijzing naar de plek waar de waarden beschikbaar worden gesteld. De verwijzing heeft de vorm van een URI conform een gekozen URI strategie. | | Ja |
| 'Definitie' | Project, Basismodel, Toepassing, Domein, View, Extern, Intern | Nee | De beschrijving van de betekenis van de construct zoals gespecificeerd in de catalogus van de desbetreffende (basis)registratie of informatiemodel. | | |
| 'Endpoint beschikbaar' | Entiteittype | Nee | Voorziening waarmee kan worden aangegeven dat er voor een entiteit al dan niet een resource endpoint beschikbaar is. | *'Ja'*, 'Nee' | Nee |
| 'Formeel patroon' | Tabel Element, Element, Complex datatype, Data element, Union element, Datatype Primitief datatype | Nee | Formele notatie in de vorm van een reguliere expressie van het gegevenspatroon van een element. | | Nee |
| 'Groepsnaam' | Groep | Nee | Voorziening om een groep aangepaste naam te kunnen geven. | | Nee |
| 'Herkomst' | Entiteittype | Ja | **Wie kan hier een definitie van geven ?** | | Ja |
| 'Imvertor' | Basismodel, Toepassing | Nee | **Wie kan hier een definitie van geven ?** | | Nee |
| 'Indicatie authentiek' | Element, Groep, Relatie | Nee | Aanduiding of het een authentiek gegeven (attribuutsoort) betreft. | | Ja |
| 'Indicatie formele historie' | Element, Groep, Relatie | Ja | Voorziening waarmee aangegeven kan worden of formele historie van toepassing is op de constructie. | 'Ja', *'Nee'*, 'Zie groep', 'N.v.t.' | Ja |
| 'Indicatie kerngegeven' | Element, Groep, Relatie, Relatie-entiteit | Nee | Indicatie om aan te kunnen geven of een gegeven deel uit maakt van de matchgegevens. Een groep van gegevens waarmee een entiteit gevonden kan worden. Heeft alleen een toepassing binnen StUF schema's. Deprecated. | 'Ja', *'Nee'* | Ja |
| 'Indicatie matchgegeven' | Element, Groep, Relatie, Relatie-entiteit | Nee | Indicatie dat het gegeven noodzakelijk is voor het kunnen identificeren van een object. Heeft alleen een toepassing binnen StUF schema's. | 'Ja', *'Nee'* | Ja |
| 'Indicatie materiÃ«le historie' | Element, Groep, Relatie | Ja | Voorziening waarmee aangegeven kan worden of materiÃ«le historie van toepassing is op de constructie. | 'Ja', *'Nee'*, 'Zie groep', 'N.v.t.', 'Ja, zie regels' | Ja |
| 'Intern project' | Intern | Ja | **Wie kan hier een definitie van geven ?** | | Nee |
| 'Interne naam' | Intern | Ja | **Wie kan hier een definitie van geven ?** | | Nee |
| 'Interne release' | Intern | Ja | **Wie kan hier een definitie van geven ?** | | Nee |
| 'Is afgeleid' | Project, Basismodel, Toepassing, Domein, Extern, Intern, Entiteittype, Relatie, Data element, Element, Gegevensgroep, Tabel-entiteit, Tabel Element, Union, Union element, Enumeration, Enum, Groep, Relatie-entiteit, Complex datatype, Datatype Primitief datatype, Interface | Nee | Deze constructie is al dan niet afgeleid van een "supplier model". Wanneer je niks opgeeft wordt afleiding vastgesteld op basis van het package waarin het voorkomt. | 'Nee', 'Ja', *'Zie package'* | Nee |
| 'Is includeerbaar' | Product | Nee | Deze constructie kan via xi:include worden geincludeerd in het document. De equivalente constructie in het XML schema, of constructies daarbinnen, krijgt hierdoor dan een optioneel attribuut xml:base bijgevoegd. | 'Ja', *'Nee'* | JaJa |
| 'Lengte' | Element, Data element, Datatype Primitief datatype | Nee | De maximale lengte die een attribuut kan hebben. | | Nee |
| 'Maximum waarde (inclusief)' | Element, Data element, Datatype Primitief datatype | Nee | DDe maximale waarde (inclusief) dat een attribuut mag hebben. | | Nee |
| 'Minimum lengte' | Element, Data element, Datatype Primitief datatype | Nee | De minimale lengte die een attribuut moet hebben. | | Nee |
| 'Minimum waarde (inclusief)' | Element, Data element, Datatype Primitief datatype | Nee | De minimale waarde (inclusief) dat een attribuut moet hebben | | Nee |
| 'Mogelijk geen waarde' | Element, Groep, Relatie | Nee | Indicatie waarmee wordt aangegeven dat het gegeven ook geen waarde kan hebben. | 'Ja', *'Nee'* | Ja |
| 'Naam' | Project, Basismodel, Toepassing, Domein, View, Extern, Intern | Nee | **Wie kan hier een definitie van geven ?** | | |
| 'Naam in meervoud' | Entiteittype | Ja | Voorziening om een entiteit een meervoudsnaam te kunnen geven. Deze wordt gebruikt als propertynaam van een entiteit in het yaml bestand. | | |
| 'Niveau' | Basismodel | Nee | Het niveau is een waarde uit een beperkte set: "algemeen" betekent dat het model een fundament is van een ander model en moet worden opgenomen. Het modelleert generieke constructies die deel uitmaken van de echte wereld. Dit omvat meestal abstracte object typen. Het kan andere constructen bevatten. "specifiek" betekent dat het model een bepaald domein beschrijft of een samenhangend deel ervan . | 'generiek', *'specifiek'* | Nee |
| 'Omschrijving' 'Toelichting' | Project, Basismodel, Toepassing, Domein, View, Extern, Intern | Nee | Aanvullende beschrijving van het construct met de bedoeling dat te verduidelijken. | | |
| 'Patroon' | Element, Complex datatype, Data element, Union element, Datatype Primitief datatype | Nee | Beschrijving van het gegevenspatroon van een element. Dit kan de basis zijn voor een reguliere expressie. | | Nee |
| 'Positie' | Domein, Extern, Intern, Entiteittype, Relatie, Data element, Element, Tabel-entiteit, Tabel Element, Union, Union element, Enumeration, Enum, Relatie-entiteit, Complex datatype, Datatype Primitief datatype, Interface | Nee | De positie van de construct binnen producten waarin deze opeenvolging een rol speelt. | | Ja |
| 'Ref-release' | Domein, View, Extern | Nee | **Wie kan hier een definitie van geven ?** | | Nee |
| 'Ref-version' | Domein, View, Extern | Nee | **Wie kan hier een definitie van geven ?** | | Nee |
| 'Release' | Basismodel, Toepassing, Domein, View, Extern, Intern | Basismodel, Toepassing, Domein, View, Intern | Dit bevat de releasedatum in het format yyyymmdd . De releasedatum wordt mede gebruikt om een model, koppelvlak of bericht uniek te identificeren in Imvertor. | Bijv. '20170901' | Nee |
| 'Restriction identifier' | Entiteittype, Relatie, Element, Groep, Groep compositie, Relatie-entiteit, Tabel-entiteit, Tabel Element, Enumeration, Datatype Primitief datatype, Complex datatype, Union, Data element, Union element, Enum | Nee | Een label dat aan een construct kan worden toegekend om onderscheid mogelijk te maken tussen aangescherpte constructs die afgeleid zijn van eenzelfde construct. Heeft alleen een functie bij het genereren van StUF schema's. | | Ja |
| 'Supplier-name' | Basismodel, Toepassing | Toepassing | Dit bevat de naam van het suppliermodel waarvan een model hergebruik maakt. Er zijn meerdere waardes mogelijk, gescheiden door een ; (puntkomma) Volgorde moet corresponderen met die in Supplier-project en Supplier-release. Alleen opnemen wanneer van afleiding sprake is. | Bijv. 'SIM;SIM' | Nee |
| 'Supplier-package-name' | Domein, View | Nee | De naam van de supplier (domein of view) package. Deze naam wordt opgegeven als deze niet gelijk is aan de naam van het package waar de tagged value op geplaatst is. | | Nee |
| 'Supplier-project' | Basismodel, Toepassing | Toepassing | Dit bevat de naam van project waarbinnen het suppliermodel waarvan een model hergebruik maakt is opgenomen. Er zijn meerdere waardes mogelijk, gescheiden door een ; (puntkomma) . Volgorde moet corresponderen met die in Supplier-name en Supplier-release. Alleen opnemen wanneer van afleiding sprake is. | Bijv. 'RSGB;IMztc' | Nee |
| 'Supplier-release' | Basismodel, Toepassing | Toepassing | Dit bevat de releasedatum in het format yyyymmdd van het suppliermodel waarvan een model hergebruik maakt. Er zijn meerdere waardes mogelijk, gescheiden door een ; (puntkomma) . Volgorde moet corresponderen met die in supplier-name en supplier-project. Alleen opnemen wanneer van afleiding sprake is. | Bijv. '20170901;20170801' | Nee |
| 'Target role in meervoud' | Relatie | Ja | Voorziening om de target role een meervoudsnaam te kunnen geven. Deze wordt gebruikt als propertynaam van een relatie in het yaml bestand. | | |
| 'Verkorte alias' | Toepassing, Basismodel | Toepassing, | Verkorte alias is een korte naam, die uiteindelijk gekoppeld is aan een namespace in XML schema. In feite is het dus een technisch configuratie-element. Heeft alleen een toepassing binnen StUF schema's. | | Nee |
| 'Versie ID' | Basismodel, Toepassing, Domein, Extern, View | Nee | De identificatie van de versie/revisie van dit model of model-element in het gehanteerde versiebeheersysteem. | | Nee |
| 'Web locatie' | Basismodel, Toepassing, Extern, View, Domein | Nee | **Wie kan hier een definitie van geven ?** | | Ja |

## 7.3. Tagged values voor de BSM (Bericht Structuur Modellen)

[**Terug naar top**](#7-tagged-values)

| Tagged value naam | Waar | Verplicht (in) | Beschrijving | Mogelijke waarden _(in vet de defaultwaarde)_ | Afleiding mogelijk |
| --- | --- | --- | --- | --- | --- |
| 'aanvullendeElementen genereren' | Toepassing Koppelvlak | Nee | Geeft aan of er in de XML-schema's 'aanvullendeElementen' elementen moeten worden mee gegenereerd. Standaard worden deze optioneel mee gegenereerd. Kan alleen op Koppelvlak niveau worden gedefinieerd. Heeft alleen een functie bij het genereren van StUF schema's. | 'Nee', *'Ja'* | |
| 'Afkorting' | Basismodel, Toepassing Koppelvlak, Domein, View | Nee | Afkorting van dit model. Deze afkorting wordt o.a. gebruikt waar informatie over het model wordt gepubliceerd. | | Ja |
| 'Beheerder' | Extern | Nee | Naam van de beheerder van het model. | | Ja |
| 'beheerder_email' | Toepassing Koppelvlak | Nee | e-Mailadres van de beheerder van het koppelvlak. | | Nee |
| 'Berichtcode' | Vraagberichttype, Antwoordberichttype, Kennisgevingberichttype, Synchronisatieberichttype, Vrij berichttype, Getberichttype, Patchberichttype, Postberichttype, Putberichttype, Deleteberichttype | Ja | Code waarmee de aard van een bericht uniek geidentificeerd kan worden. | 'Bv01', 'Bv02', 'Bv03', 'Bv04', 'De01', 'Di01', 'Di02', 'Du01', 'Du02', 'Fo01', 'Fo02', 'Fo03', 'Gc01', 'Gc02', 'Gr01', 'La01', 'La02', 'La03', 'La04', 'La05', 'La06', 'La07', 'La08', 'La09', 'La10', 'La11', 'La12', 'La13', 'La14', 'Lk01', 'Lk02', 'Lk03', 'Lk04', 'Lk05', 'Lk06', 'Lv01', 'Lv02', 'Lv03', 'Lv04', 'Lv05', 'Lv06', 'Lv07', 'Lv08', 'Lv09', 'Lv10', 'Lv11', 'Lv12', 'Lv13', 'Lv14', 'Pa01', 'Po01', 'Pu01', 'Sa01', 'Sa02', 'Sa03', 'Sa04', 'Sh01', 'Sh02', 'Sh03', 'Sh04', 'Tr01' | Nee |
| 'Bijzonderheden' | Vraagberichttype, Antwoordberichttype, Kennisgevingberichttype, Synchronisatieberichttype, Vrij berichttype | Nee | Opnemen ter documentatie van een bericht. | | Nee |
| 'custom_path_facet' | Padtype | Nee | Het deel van de messagenaam dat niet uit het model afgeled kan worden. Om de messagenaam toch te kunnen verifieren tegen het model wordt daar eerst de custom_path_facet uit verwijderd. Deze tv mag â€˜/â€™ (slashes) bevatten maar niet aan het begin en eind. | | Nee |
| 'Definitie' | Project, Basismodel, Toepassing Koppelvlak, Domein, View, Extern, Intern | Nee | De beschrijving van de betekenis van de construct zoals gespecificeerd in de catalogus van de desbetreffende (basis)registratie of informatiemodel. | | |
| 'Data locatie' | Extern, View | View | De locatie waar informatie over de gegevens van een construct te vinden zijn. Wanneer het een external of view package betreft: De verwijzing naar de locatie van het bijbehorende informatiemodel waar dit package een representatie van is. In alle andere gevallen moet het een waardenlijst betreffen. Het gaat dan om de verwijzing naar de plek waar de waarden beschikbaar worden gesteld. De verwijzing heeft de vorm van een URI conform een gekozen URI strategie. | | Ja |
| 'Direct gevolg' | Vraagberichttype, Antwoordberichttype, Kennisgevingberichttype, Synchronisatieberichttype, Vrij berichttype | Nee | Opnemen ter documentatie van een bericht. | | Nee |
| 'e-types genereren' | Toepassing Koppelvlak | Nee | Geeft aan of de -e complexTypes in de XML-schema's mee gegenereerd moeten worden. Standaard worden deze mee gegenereerd. Kan alleen op Koppelvlak niveau worden gedefinieerd. Heeft alleen een functie bij het genereren van StUF schema's. | 'Nee', *'Ja'* | |
| 'Endpoint beschikbaar' | Entiteittype | Nee | Voorziening waarmee kan worden aangegeven dat er voor een entiteit al dan niet een resource endpoint beschikbaar is. | *'Ja'*, 'Nee' | Nee |
| 'Example' | Element | Nee | Voorbeeldwaarde van een property. | | Nee |
| 'extraElementen genereren' | Toepassing Koppelvlak | Nee | Geeft aan of er in de XML-schema's 'extraElementen' elementen moeten worden mee gegenereerd. Standaard worden deze optioneel mee gegenereerd. Kan alleen op Koppelvlak niveau worden gedefinieerd. Heeft alleen een functie bij het genereren van StUF schema's. | 'Nee', *'Ja'* | |
| 'Formeel patroon' | Tabel Element, Element, Complex datatype, Data element, Union element, Datatype Primitief datatype | Nee | Formele notatie in de vorm van een reguliere expressie van het gegevenspatroon van een element. | | Nee |
| 'Functie berichtrelatie' | Berichtrelatie | Nee | Geeft het karakter aan van de berichtrelatie. Heeft alleen een functie bij StUF schema generatie. | 'update', 'selectie', *'antwoord'* | Nee |
| 'Functie entiteitrelatie' | Entiteitrelatie | Nee | Geeft het karakter aan van de entiteitrelatie. Heeft alleen een functie bij StUF schema generatie. | 'entiteit' | Nee |
| 'Groepsnaam' | Groep | Nee | Voorziening om een groep aangepaste naam te kunnen geven. | | Nee |
| 'Grouping' | Getberichttype | Nee | Indicatie waarmee wordt aangegeven of de response meerdere resultaten kan teruggeven (collection) of slechts 1 resultaat (resource). | 'resource', 'collection' | Nee |
| 'Herkomst' | Entiteittype | Ja | **Wie kan hier een definitie van geven ?** | | Ja |
| 'Imvertor' | Basismodel, Toepassing Koppelvlak | Nee | **Wie kan hier een definitie van geven ?** | | Nee |
| 'Indicatie authentiek' | Element, Groep, Relatie | Nee | Aanduiding of het een authentiek gegeven (attribuutsoort) betreft. | | Ja |
| 'Indicatie formele historie' | Element, Groep, Relatie | Ja | Voorziening waarmee aangegeven kan worden of formele historie van toepassing is op de constructie. | 'Ja', *'Nee'*, 'Zie groep', 'N.v.t.' | Ja |
| 'Indicatie in onderzoek' | Element, Groep, Relatie | Ja | De indicatie of te bevragen is dat er twijfel is of is geweest aan de juistheid van de attribuutwaarde en dat een onderzoek wordt of is uitgevoerd naar de juistheid van de attribuutwaarde. | | Ja |
| 'Indicatie kerngegeven' | Element, Groep, Relatie, Relatie-entiteit | Nee | Indicatie om aan te kunnen geven of een gegeven deel uit maakt van de matchgegevens. Een groep van gegevens waarmee een entiteit gevonden kan worden. Heeft alleen een toepassing binnen StUF schema's. Deprecated. | 'Ja', *'Nee'* | Ja |
| 'Indicatie matchgegeven' | Element, Groep, Relatie, Relatie-entiteit | Nee | Indicatie dat het gegeven noodzakelijk is voor het kunnen identificeren van een object. Heeft alleen een toepassing binnen StUF schema's. | 'Ja', *'Nee'* | Ja |
| 'Indicatie materiÃ«le historie' | Element, Groep, Relatie | Ja | Voorziening waarmee aangegeven kan worden of materiÃ«le historie van toepassing is op de constructie. | 'Ja', *'Nee'*, 'Zie groep', 'N.v.t.', 'Ja, zie regels' | Ja |
| 'Intern project' | Intern | Ja | **Wie kan hier een definitie van geven ?** | | Nee |
| 'Interne naam' | Intern | Ja | **Wie kan hier een definitie van geven ?** | | Nee |
| 'Interne release' | Intern | Ja | **Wie kan hier een definitie van geven ?** | | Nee |
| 'Is afgeleid' | Project, Basismodel, Toepassing Koppelvlak, Domein, Extern, Intern, Entiteittype, Relatie, Data element, Element, Gegevensgroep, Tabel-entiteit, Tabel Element, Union, Union element, Enumeration, Enum, Groep, Relatie-entiteit, Complex datatype, Datatype Primitief datatype, Interface | Nee | Deze constructie is al dan niet afgeleid van een "supplier model". Wanneer je niks opgeeft wordt afleiding vastgesteld op basis van het package waarin het voorkomt. | 'Nee', 'Ja', *'Zie package'* | Nee |
| 'Is includeerbaar' | Product | Nee | Deze constructie kan via xi:include worden geincludeerd in het document. De equivalente constructie in het XML schema, of constructies daarbinnen, krijgt hierdoor dan een optioneel attribuut xml:base bijgevoegd. | 'Ja', *'Nee'* | JaJa |
| 'Koppelvlak-naam' | Toepassing Koppelvlak | Ja | De naam van het koppelvlak. | | Nee |
| 'Lege enumeration toegestaan' | Enumeration, Toepassing Koppelvlak | Nee | Geeft aan of er aan elke enumeratie simpleType ook een lege enumeratie toegevoegd moet worden. Standaard wordt dit mee gegenereerd. Kan zowel op Koppelvlak niveau als op enumeration niveau worden gedefinieerd waarbij die op attribuutniveau die op op Koppelvlak niveau overrulled. Heeft alleen een functie bij het genereren van StUF schema's. | 'Nee', *'Ja'* | |
| 'Lengte' | Element, Data element, Datatype Primitief datatype | Nee | De maximale lengte die een attribuut kan hebben. | | Nee |
| 'Maximum waarde (inclusief)' | Element, Data element, Datatype Primitief datatype | Nee | DDe maximale waarde (inclusief) dat een attribuut mag hebben. | | Nee |
| 'Minimum lengte' | Element, Data element, Datatype Primitief datatype | Nee | De minimale lengte die een attribuut moet hebben. | | Nee |
| 'Minimum waarde (inclusief)' | Element, Data element, Datatype Primitief datatype | Nee | De minimale waarde (inclusief) dat een attribuut moet hebben | | Nee |
| 'Mogelijk geen waarde' | Element, Groep, Relatie | Nee | Indicatie waarmee wordt aangegeven dat het gegeven ook geen waarde kan hebben. | 'Ja', *'Nee'* | Ja |
| 'Naam' | Project, Basismodel, Toepassing Koppelvlak, Domein, View, Extern, Intern | Nee | **Wie kan hier een definitie van geven ?** | | |
| 'Naam in meervoud' | Entiteittype | Ja | Voorziening om een entiteit een meervoudsnaam te kunnen geven. Deze wordt gebruikt als propertynaam van een entiteit in het yaml bestand. | | |
| 'Niveau' | Basismodel | Nee | Het niveau is een waarde uit een beperkte set: "algemeen" betekent dat het model een fundament is van een ander model en moet worden opgenomen. Het modelleert generieke constructies die deel uitmaken van de echte wereld. Dit omvat meestal abstracte object typen. Het kan andere constructen bevatten. "specifiek" betekent dat het model een bepaald domein beschrijft of een samenhangend deel ervan . | 'generiek', *'specifiek'* | Nee |
| 'noValue toegestaan' | Toepassing Koppelvlak | Nee | Geeft aan of het StUF:noValue attribute in de XML-schema's mee gegenereerd wordt. Standaard wordt dit mee gegenereerd. Kan alleen op Koppelvlak niveau worden gedefinieerd. Heeft alleen een functie bij het genereren van StUF schema's. | 'Nee', *'Ja'* | |
| 'Omschrijving' 'Toelichting' | Project, Basismodel, Toepassing Koppelvlak, Domein, View, Extern, Intern | Nee | Aanvullende beschrijving van het construct met de bedoeling dat te verduidelijken. | | |
| 'Page' | Getberichttype | Nee | Indicatie waarmee wordt aangegeven of de response geschikt moet zijn voor hal+json pagination. Natuurlijk alleen van toepassing als de serialisatie ook hal+json is. | 'true', 'false' | Nee |
| 'Patroon' | Element, Complex datatype, Data element, Union element, Datatype Primitief datatype | Nee | Beschrijving van het gegevenspatroon van een element. Dit kan de basis zijn voor een reguliere expressie. | | Nee |
| 'Positie' | Domein, Extern, Intern, Entiteittype, Relatie, Data element, Element, Tabel-entiteit, Tabel Element, Union, Union element, Enumeration, Enum, Relatie-entiteit, Complex datatype, Datatype Primitief datatype, Interface | Nee | De positie van de construct binnen producten waarin deze opeenvolging een rol speelt. | | Ja |
| 'project_url' | Toepassing Koppelvlak | Nee | Url van het bij het koppelvlak horende GitHub project. | | Nee |
| 'Ref-release' | Domein, View, Extern | Nee | **Wie kan hier een definitie van geven ?** | | Nee |
| 'Ref-version' | Domein, View, Extern | Nee | **Wie kan hier een definitie van geven ?** | | Nee |
| 'Release' | Basismodel, Toepassing Koppelvlak, Domein, View, Extern, Intern | Basismodel, Toepassing Koppelvlak, Domein, View, Intern | Dit bevat de releasedatum in het format yyyymmdd . De releasedatum wordt mede gebruikt om een model, koppelvlak of bericht uniek te identificeren in Imvertor. | Bijv. '20170901' | Nee |
| 'Restriction identifier' | Entiteittype, Relatie, Element, Groep, Groep compositie, Relatie-entiteit, Tabel-entiteit, Tabel Element, Enumeration, Datatype Primitief datatype, Complex datatype, Union, Data element, Union element, Enum | Nee | Een label dat aan een construct kan worden toegekend om onderscheid mogelijk te maken tussen aangescherpte constructs die afgeleid zijn van eenzelfde construct. Heeft alleen een functie bij het genereren van StUF schema's. | | Ja |
| 'serialisatie' | Toepassing Koppelvlak | Nee | Het JSON formaat waarin het koppelvlak uitgevoerd moet worden. | 'hal+json', 'json' | Nee |
| 'servicename' | Vraagberichttype, Antwoordberichttype, Kennisgevingberichttype, Synchronisatieberichttype, Vrij berichttype, Getberichttype, Patchberichttype, Postberichttype, Putberichttype, Deleteberichttype | Nee | OperationId van de OAS3 service. | | Nee |
| 'Sort' | Getberichttype | Nee | Indicatie waarmee wordt aangegeven of de request parameter 'Sort' moet worden opgenomen in het bericht. | 'true', 'false' | Nee |
| 'Supplier-name' | Basismodel, Toepassing Koppelvlak | Toepassing Koppelvlak | Dit bevat de naam van het suppliermodel waarvan een model hergebruik maakt. Er zijn meerdere waardes mogelijk, gescheiden door een ; (puntkomma) Volgorde moet corresponderen met die in Supplier-project en Supplier-release. Alleen opnemen wanneer van afleiding sprake is. | Bijv. 'SIM;SIM' | Nee |
| 'Supplier-package-name' | Domein, View | Nee | De naam van de supplier (domein of view) package. Deze naam wordt opgegeven als deze niet gelijk is aan de naam van het package waar de tagged value op geplaatst is. | | Nee |
| 'Supplier-project' | Basismodel, Toepassing Koppelvlak | Toepassing Koppelvlak | Dit bevat de naam van project waarbinnen het suppliermodel waarvan een model hergebruik maakt is opgenomen. Er zijn meerdere waardes mogelijk, gescheiden door een ; (puntkomma) . Volgorde moet corresponderen met die in Supplier-name en Supplier-release. Alleen opnemen wanneer van afleiding sprake is. | Bijv. 'RSGB;IMztc' | Nee |
| 'Supplier-release' | Basismodel, Toepassing Koppelvlak | Toepassing Koppelvlak | Dit bevat de releasedatum in het format yyyymmdd van het suppliermodel waarvan een model hergebruik maakt. Er zijn meerdere waardes mogelijk, gescheiden door een ; (puntkomma) . Volgorde moet corresponderen met die in supplier-name en supplier-project. Alleen opnemen wanneer van afleiding sprake is. | Bijv. '20170901;20170801' | Nee |
| 'tag' | Getberichttype, Patchberichttype, Postberichttype, Putberichttype, Deleteberichttype | Ja | Naam waarmee een aantal gerelateerde berichten gegroepeerd worden. | | Nee |
| 'Target role in meervoud' | Relatie | Ja | Voorziening om de target role een meervoudsnaam te kunnen geven. Deze wordt gebruikt als propertynaam van een relatie in het yaml bestand. | | |
| 'tijdstipRegistratie genereren' | Toepassing Koppelvlak | Nee | Geeft aan of en zo ja hoe in de XML-schema's de 'tijdstipRegistratie' elementen worden mee gegenereerd. Standaard worden deze optioneel mee gegenereerd. Kan alleen op Koppelvlak niveau worden gedefinieerd. Heeft alleen een functie bij het genereren van StUF schema's. | 'Nee', *'Optioneel'*, 'Verplicht' | |
| 'tijdvakGeldigheid genereren' | Toepassing Koppelvlak | Nee | Geeft aan of en zo ja hoe in de XML-schema's de 'tijdvakGeldigheid' elementen worden mee gegenereerd. Standaard worden deze optioneel mee gegenereerd. Kan alleen op Koppelvlak niveau worden gedefinieerd. Heeft alleen een functie bij het genereren van StUF schema's. | 'Nee', *'Optioneel'*, 'Verplicht' | |
| 'toelichting opnemen vanaf' | Toepassing Koppelvlak | Nee | Het model vanaf waar de toelichting moet worden opgenomen. | *'SIM'*, 'UGM', 'BSM' | Nee |
| 'Trigger' | Vraagberichttype, Antwoordberichttype, Kennisgevingberichttype, Synchronisatieberichttype, Vrij berichttype | Nee | Opnemen ter documentatie van een bericht. | | Nee |
| 'Verkorte alias' | Toepassing Koppelvlak, Basismodel | Toepassing Koppelvlak, | Verkorte alias is een korte naam, die uiteindelijk gekoppeld is aan een namespace in XML schema. In feite is het dus een technisch configuratie-element. Heeft alleen een toepassing binnen StUF schema's. | | Nee |
| 'Versie ID' | Basismodel, Toepassing Koppelvlak, Domein, Extern, View | Nee | De identificatie van de versie/revisie van dit model of model-element in het gehanteerde versiebeheersysteem. | | Nee |
| 'Voorwaarde' | Toepassing Koppelvlak, Vraagberichttype, Antwoordberichttype, Kennisgevingberichttype, Synchronisatieberichttype, Vrij berichttype | Nee | Opnemen ter documentatie van een bericht. | | Nee |
| 'Web locatie' | Basismodel, Toepassing Koppelvlak, Extern, View, Domein | Nee | **Wie kan hier een definitie van geven ?** | | Ja |
