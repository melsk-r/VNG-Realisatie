---
layout: page-with-side-nav
title: Installatie
---
# Installatie

## 1.1. Enterprise Architect configureren.

Om EA te gebruiken binnen de nieuwe aanpak zijn er een aantal handelingen vereist. 
Ten eerste moet EA geïnstalleerd worden. Daarna moeten er een aantal externe tools en profiles geïmporteerd worden en ten slotte moeten er enkele configuratie acties binnen EA worden uitgevoerd. Deze handelingen worden hieronder beschreven.

### 1.1.1. Installeren EA 

Het installatiescript is te vinden in de lijst bestanden onderaan deze pagina: [easetupfull151.msi](https://kinggemeenten.plan.io/attachments/161807) 
Wij werken met versie 15.2. Als je deze al geïnstalleerd hebt hoef je EA natuurlijk niet opnieuw te installeren.

Standaard worden alle attributen in EA alfabetisch gesorteerd.
Binnen de nieuwe aanpak willen we dit niet en daarom moet deze instelling uitgezet worden.
Deselecteer daarom de 'Sort Features Alphabetically' checkbox in de 'Objects' pagina van het 'Options' dialog (Start > Desktop > Preferences > Objects).

### 1.1.2. EA Toolpack installeren

De nieuwste versie van dit script kan kostenloos worden opgehaald op de website van Geert Bellekens, https://bellekens.com/ . Ga naar downloads en voeg EA Toolpack toe aan de winkelwagen. De website gebruikt een webshop om downloads aan te bieden. Het is niet verplicht een account aan te maken maar even naam en organisatie invullen moet wel. Na "afrekenen" kun je het bestand downloaden.

Voor het gemak is de versie die beschikbaar was op 1-10-2020 (EAToolPack_Setup-v2.1.18.0-tmmzea.msi) ook [hier](https://kinggemeenten.plan.io/attachments/162054) te downloaden.

### 1.1.3. Imvertor Addin installeren

De nieuwste versie van deze Addin kan kostenloos worden opgehaald van het [Imvertor Dashboard](https://armatiek.nl/Imvertor/download/EAImvertorAddinSetup.exe). De versie die beschikbaar was op 1-10-2020 vind je echter ook [hier](https://kinggemeenten.plan.io/attachments/162055). De documentatie over deze Addin en het gebruik vind je [hier](https://imvertor.armatiek.nl/imvertor-executor/dashboard/wiki?key=info-DOCIMVTOPEA).

### 1.1.4. Profielen/Metamodellen MIG en MUG importeren

De volgende metamodellen zijn beschikbaar (zie gelinkte bestanden):
1. [Metamodel Informatiemodellen Gemeenten VNG-R](https://kinggemeenten.plan.io/attachments/161644) (MIG), deze wordt binnenkort vervangen door het MIM Metamodel
2. [Metamodel Informatiemodellen Modellering](https://kinggemeenten.plan.io/attachments/162059) (MIM)
3. [Metamodel UitwisselingsGegevensmodel VNG-R](https://kinggemeenten.plan.io/attachments/162051) (MUG)
4. [Metamodel BerichtGevensmodel VNG-R](https://kinggemeenten.plan.io/attachments/161411) (MBG)

Welke je moet installeren is afhankelijk van of je model een op het MIG of afhankelijk van een op het MIG gebaseerd model is of juist van een model dat gebaseerd is op het MIM. In het eerste geval installeer je de metamodellen 1, 3 en 4 en in het tweede geval 2, 3 en 4.

In Enterprise Architect kan je via *Specialize | Technology | Publish-Tech | Import MDG Technology* de profielen met de metamodellen voor de diverse model-varianten importeren. 

![MDG-Technology][MDG-Technology1]

Let er wel op dat je de *"Import to User"* gebruikt, dan heb je immers in ieder project dat je opent of nieuw maakt de beschikking over deze profielen. 

De Metamodellen komen dan beschikbaar in de Toolbox.

Noot: als je een profiel wilt verwijderen, dan kan je dat als volgt doen:
* als het profiel alleen in het 'model' is geïmporteerd dan kan het binnen Sparx verwijderd worden: "Specialize | Technology | Manage-Tech" (remove)
* als het profiel in ‘User’ is opgenomen, dan moeten de bestanden handmatig worden verwijderd. Open Windows Explorer en ga naar %APPDATA%\Sparx Systems\EA\MDGTechnologies. Daarbij is %APPDATA% over het algemeengelijk aan "C:\Users\%username%\AppData\Roaming\". Dus bijvoorbeeld: "C:\Users\Jans_J\AppData\Roaming\Sparx Systems\EA\MDGTechnologies".
Let op: de AppData folder is normaliter HIDDEN!
Verwijder vervolgens het betrefende MDG.bestand (bijvoorbeeld MIG of MUG).

### 1.1.5. Activatie metamodellen

Na het laden van de MIG en MUG metamodellen (zie boven) moeten deze geactiveerd worden in de configuratie van de Schema Composer.  Deze is te bereiken via *Specialize | Technologies | Manage-Tech*.

![MDG technologies][MDG_technologies]

In geval er meerdere MUG-profielen zichtbaar zijn in het configuratiescherm moeten deze alle aangevinkt worden wegens een onbekende bug in EA.

Tevens moet in en overbodige profielen uitgezet worden. De profielen die minimaal actief moeten zijn, zijn:
* 'Basic UML 2 Technology'
* 'Core Extensions'
* 'MIG' of 'MIM'
* 'MUG'
* 'MBG'

### 1.1.6. Aanpassen metamodellen

Zo nu en dan moeten de metamodellen worden aangepast. Bijv. omdat er nieuwe stereotypes geconfigureerd moeten worden.
Het toevoegen van nieuwe stereotypes kan pas gebeuren nadat dit goed is afgestemd met elkaar aangezien nieuwe stereotypes kunnen conflicteren met het MIG.

De metamodellen maar ook het EA project van waaruit de metamodellen aangepast worden zijn opgeslagen in de [KING Metamodellen en profielen SVN repository](https://kinggemeenten.plan.io/svn/stuf-schemagenerator/KING%20Metamodel%20en%20profielen). Daar vindt je ook een handleiding hoe je vanuit het EA project de MDG profielen genereert.

### 1.1.7. SVN configureren voor EA

Hieronder worden de stappen beschreven die je moet doorlopen om Enterprise Architect geschikt te maken voor het werken met Subversion.

* Enterprise Architect werkt direct op subversion en niet met Tortoise. Je moet er dus voor zorgen dat je over de SVN executable ‘svn.exe’ beschikt. Dit kan door Tortoise te installeren. Heb je Tortoise al geïnstalleerd dan is de kans groot dat je de svn command line client niet hebt geïnstalleerd.  Installeer daarom Tortoise opnieuw of download de laatste versie van Tortoise en installeer deze. Selecteer daarbij in het Tortoise setup menu de optie ‘Will be installed on local hard drive’ bij ‘command line client tools’ en start daarna opnieuw op:

![Tortoise setup][TortoiseSetup]

* Hierna dien je een working copy aan te maken in je filesysteem van de inmiddels vervaardigde EAP repository. Kies daarvoor eerst de gewenste locatie en creëer zo nodig een folder;
* Binnen de zojuist gekozen of vervaardigde folder check je vervolgens de repository met de EAP bestanden uit (op dit moment kun je deze vinden onder https://vngrealisatie.plan.io/svn/modellen-repository.modellen-repository), Kies daarbij een naam voor de folder waarin deze moet worden uitgepakt (bijv. ‘EAP-bronnen’). Er worden nu lokaal een aantal folders en bestanden geplaatst;
* We gaan nu in EA een aantal versioncontrol configuraties aanmaken die je in de gelegenheid stellen eenvoudig naar de subversion folders te navigeren. Afhankelijk van welke modellen je denkt te gaan produceren moet je enkele of alle volgende configuraties aanmaken voor de volgende folders: 
  * trunk/SIM;
  * trunk/UGM;
  * trunk/BSM;
  * branches/SIM;
  * branches/UGM;
  * branches/BSM;
  * tags/SIM;
  * tags/UGM;
  * tags/BSM.
* Open daarvoor in Enterprise Architect het lege template EA bestand dat je onderaan deze pagina in de bestandslijst kunt vinden. Hier gaan we niets mee doen maar:
  * een geopend EA bestand is een voorwaarde om SVN in Enterprise Architect te configureren;
  * het voorziet je al van de genoemde SVN configuraties die je dan alleen nog maar hoeft te vullen.
* Ga binnen Enterprise Architect naar ‘Configure | Version Control | Project-VC’. 
Je krijgt nu het volgende menu: ![EA Version Control Settings][EA-Version-Control-Settings] Waarbij je bij de 'Defined Configurations' dus al de negen genoemde configuraties ziet staan (in de illustratie hierboven is deze echter leeg).

* Voor elk van deze negen configuraties doe je nu het volgende:
  * Selecteer de configuratie;
  * Bepaal of de configuratie voor jou van toepassing zal zijn. Als je je nooit bezig houdt met het ontwikkelen van SIM's, heb je de configuratie 'Imvertor-trunk-SIM' niet nodig. Indien dit niet het geval is verwijder hem dan.
  * Indien de configuratie wel van toepassing is geef dan aan dat het version control van het type ‘Subversion’ is;
  * Kies het path naar de gerelateerde SVN folder. Helaas kan je daarbij geen copy and paste van een voorgaand path toepassen;
  * Geef aan waar de ‘svn.exe’ nu staat (dit hoef je waarschijnlijk alleen bij de eerste configuratie te doen); ![Version Control Settings][Version-Control-Settings]
  * Bewaar de configuratie. 
De volgorde waarin de configuraties zijn opgevoerd is bepalend voor de volgorde waarin deze verschijnen in het pull-down menu voor het ophalen van de packages. Indien je het meest modellen uit de tags ophaalt dan is het wellicht handiger om de configuraties 'Imvertor-tags-SIM', 'Imvertor-tags-UGM' en 'Imvertor-tags-BSM' als eerste op te voeren. In dat geval zul je de oude configuraties toch moeten verwijderen en de configuraties helemaal zelf op moeten voeren.

* Als je alle 9 configuraties hebt vervaardigd dan kan je het menu sluiten.

![Version Control Settings Configured][Version-Control-Settings-Configured]

### 1.1.8. Tagged value SourceAttribute navigeerbaar (klikbaar) maken 

* Ga naar _Configure | Reference Data | UML Types_, voeg daar de tag name 'SourceAttribute' toe (*Let op!* hoofdletter 'S' en 'A') met de onderstaande vulling:

![EA Sourceattribute Settings][EA-SourceattributeSettings]

* Klik op _Save_.

### 1.1.9. Traceability script beschikbaar maken in project browser.
 
p{color:red}. Het is me niet duidelijk of het traceability script nu beschikbaar gesteld wordt via de EA Toolpack of dat je deze apart moet installeren. In het laatste geval moet je i.i.g. de laatste versie van het script installeren die onderaan deze pagina is toegevoegd (Set Traceability Scripts with and without transformation 2016-08-05.xml).

Het set traceability script wordt geïmporteerd via "Configure | Model | Transfer | Import Reference Data | Shared File"

p{color:red}. *Let op*: Een herstart van EA of zelfs van je systeem kan nodig zijn om de optie 'Scripts' in je context menu bij het rechtsklikken op een package te laten verschijnen.

Als je dat gedaan hebt zal je zien dat er nu in je context menu bij het rechtsklikken op een package een optie is bijgekomen:
'Scripts' met de subopties 'Set Traceability with Transformation' en 'Set Traceability without Transformation'. Indien deze niet in de projectbrowser te zien is moeten de volgende stappen uitgevoerd worden

> Het script is te vinden onder Specialize > Scripting.
> Maak in het opkomende menu een map "Package Group" aan als "new project browser group" (als die nog niet bestaat).
> Sleep het Traceability script (Main) van "KING scripts" naar "Package Group" . 
> Nu is het script beschikbaar onder de rechtermuisknop op de Package in de project Browser (keuze scripting).

## 1.2. Aan het werk

Je bent nu klaar om aan het werk te gaan. 
Het is echter handig om eerst de hoofdstukken [2](https://kinggemeenten.plan.io/projects/de-nieuwe-aanpak/wiki/2_Begrippen)  (Begrippen) en 
[3](https://kinggemeenten.plan.io/projects/de-nieuwe-aanpak/wiki/3_Het_drie-lagen_model) (Het drie-lagen model) door te lezen. 
Daarna kun je m.b.v. hoofdstuk [4](https://kinggemeenten.plan.io/projects/de-nieuwe-aanpak/wiki/4_De_nieuwe_werkwijze) (De nieuwe werkwijze) daadwerkelijk aan de slag.


[MDG-Technology1]: https://kinggemeenten.plan.io/attachments/download/160341/MDG-Technology1.jpg
[MDG_technologies]: https://kinggemeenten.plan.io/attachments/download/159990/MDG_technologies.png
[TortoiseSetup]: https://kinggemeenten.plan.io/attachments/download/160332/Tortoise%20Custom%20Setup.jpg
[EA-Version-Control-Settings]: https://kinggemeenten.plan.io/attachments/download/160333/EA%20Version%20Control%20Settings.jpg
[Version-Control-Settings]: https://kinggemeenten.plan.io/attachments/download/160955/Version%20Control%20Settings.png
[Version-Control-Settings-Configured]: https://kinggemeenten.plan.io/attachments/download/160956/Version%20Control%20Settings%20Configured.png
[EA-SourceattributeSettings]: https://kinggemeenten.plan.io/attachments/download/162227/sourceattribute-instellingen-ea.JPG
