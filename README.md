# Awesome Zeitreihen-Tools und Daten der Energiesystemmodellierung

# Einführung

Dieses Dokument entstand auf dem Jahrestreffen 2021 des Forschungsnetzwerks Energiesystemanalyse.
Ziel ist der Informationsaustausch für Energiesystemmodellierer zu Zeitreihen.


Um es aktuell zu halten, sind wir auf Mithilfe angewiesen. Bitte eine Issue eröffnen oder einen Pull-Request schicken, falls Sie etwas hinzufügen möchten.

# Autoren

Urheber des Dokuments sind alle Teilnehmer des Workshops "Zeitreihen-Tools und Daten der Energiesystemmodellierung" vom Jahrestreffen 2021 des Forschungsnetzwerks Energiesystemanalyse. Vielen Dank an alle Teilnehmer für die rege Mitarbeit und die spannenden Diskussionen!

Gepflegt wird das Dokument vom Team des IEK-3 des Forschungszentrums Jülich.

# Verwendung von Zeitreihen

## Verwendungszwecke von Zeitreihen

- Simulation von PV-Batteriesystem
- Berechnung des marginalen Emissionsfaktors (zeitlich/räumlich hoch aufgelöst) - für verbraucherseitige Lastverschiebung
- Berechnung von Heizbedarfsprofilen von Gebäuden (vereinfachte Simulationsmodelle basierend auf U-Werten, Standort und Wetter)
- Berechnung von Netzengpässen, Redispatchmengen (regionalisiert)
- Optimierung von Stromversorgungssystemen
- Agentenbasierte Simulation 
- Prognosemodelle über Regression
- Standorte für Power-to-Gas
- Endogener technologischer Fortschritt im Optimierungsmodell
- Quartiersweise Heizbedarfe unter Berücksichtigung von Gleichzeitigkeit
- Parameteridentifikation
- Co-Simulation (elektrische und thermische Energieversorgungssysteme, IKT und cash flows)


## Typische Eingangsdaten für die Energiesystemmodellierung

Als Anregung für eigene Modelle hier eine Liste von typischen Eingangsdaten in Energiesystemmodelle.

- Stromerzeugung (kraftwerksscharf, 15-min) DE/EU
- Last/Verbrauch (Land/TSO-Region/NUTS0-3): Wärme aufgeteilt nach Raumheizung, Brauchwarmwasser und Prozesswärme; Fernwärme aufgeteilt nach allg. Versorgung (private Haushalte und GHD) bzw. Industrie
- Wetterdaten (Strahlung, Temperatur, Windgeschwindigkeit (10 m bzw. 100..200 m), Albedo, Luftfeuchte)
- EE-Einspeisung für verschiedene Technologien der gleichen EE-Kategorie (zB. residential vs. industrial rooftop PV and utility-scale PV)
- Kosten
- Zeitreihen Hausspeichersysteme
- DSM-Zeitreihen
- Strompreis am Spotmarkt
- Netzdaten (auch auf europäischer Ebene)
- CO$_2$-Preis
- Ölpreis
- Emissionen (z.B. CO$_2$, NO$_x$)
- Betriebsprofile einzelner Technologien
- Verhaltensprofile von Personen
- Mobilitätsdaten


# Software Tools und Modelle

## Offene Modelle von OpenMod

Linksammlung von offenen Modellen

https://wiki.openmod-initiative.org/wiki/Open_Models 

## Polysun

Gebäudesimulationssystem, kommerziell, einfach bedienbar

www.velasolaris.de

## LoadProfileGenerator

Tool für agentenbasierte Modellierung von Haushaltslasten, mächtig aber komplex.

www.loadprofilegenerator.de 

## atlite

atlite is a free software, xarray-based Python library for converting weather data (like wind speeds, solar influx) into energy systems data. It has a lightweight design and works with big weather datasets while keeping the resource requirements especially on CPU and RAM resources low.
 
https://github.com/PyPSA/atlite

## emobpy

emobpy is an open-source Python tool that can create battery electric vehicle profiles. Three different time series can be created: Motor electricity consumption time series, grid availability time series and grid electricity demand time series. The electricity consumption time series are created based on mobility statistics

https://pypi.org/project/emobpy/

## feedinlib

The feedinlib is a tool to calculate feed-in time series of photovoltaic and wind power plants. It therefore provides interfaces between different weather data sets and feed-in models. It is part of the oemof group but works as a standalone application.

https://github.com/oemof/feedinlib

## demandlib

With the demandlib you can create power and heat profiles for various sectors by scaling them to your desired demand. Additionally you can specify a year so that holidays are considered respectively.

https://github.com/oemof/demandlib

## PVLib

pvlib python is a community supported tool that provides a set of functions and classes for simulating the performance of photovoltaic energy systems. pvlib python was originally ported from the PVLIB MATLAB toolbox developed at Sandia National Laboratories and it implements many of the models and methods developed at the Labs.

https://github.com/pvlib/pvlib-python

## WindPowerLib

The windpowerlib is a library that provides a set of functions and classes to calculate the power output of wind turbines. It was originally part of the feedinlib (windpower and photovoltaic) but was taken out to build up a community concentrating on wind power models.

https://github.com/wind-python/windpowerlib 

## GSEE

GSEE is a solar energy simulation library designed for rapid calculations and ease of use. Renewables.ninja uses GSEE. The development of GSEE predates the existence of pvlib-python but builds on its functionality as of v0.4.0. Use GSEE if you want fast simulations with sensible defaults and solar energy technologies other than PV, and pvlib-python if you need control over the nuts and bolts of simulating PV systems.

github.com/renewables-ninja/gsee

## tsib

tsib is a python package that builds up on different databases and models for creating consistent demand and production time series of residential buildings. This could be either occupancy behavior, electricity demand or heat demand time series as well as photovoltaic (PV) and solar thermal production time series.

https://github.com/FZJ-IEK3-VSA/tsib

## FINE

The FINE python package provides a framework for modeling, optimizing and assessing energy systems. With the provided framework, systems with multiple regions, commodities and time steps can be modeled. Target of the optimization is the minimization of the total annual cost while considering technical and enviromental constraints. Besides using the full temporal resolution, an interconnected typical period storage formulation can be applied, that reduces the complexity and computational time of the model.

https://github.com/FZJ-IEK3-VSA/FINE

## tsam

tsam is a python package which uses different machine learning algorithms for the aggregation of time series. The data aggregation can be performed in two freely combinable dimensions: By representing the time series by a user-defined number of typical periods or by decreasing the temporal resolution. tsam was originally designed for reducing the computational load for large-scale energy system optimization models by aggregating their input data, but is applicable for all types of time series, e.g., weather data, load data, both simultaneously or other arbitrary groups of time series.

https://github.com/FZJ-IEK3-VSA/tsam

## OpenEgo

A cross-grid-level electricity grid and storage optimization open-source tool. Contains the modules: eTraGo, which is an optimization tool for the transmission grid based on PyPSA (focus in Germany with over 10000 nodes of 110 kV voltages and higher); eDisGo for  the optimization of distribution grids; DING0 for generating synthetic medium and low voltage power distribution grids; and eGo Data Processing for (geo)data processing, database setup, data validation (with all the source data available in OEP).

https://github.com/openego


## Euro-Calliope

A model of the European electricity system built using Calliope.
Lizenz: MIT / CC-BY
https://github.com/calliope-project/euro-calliope

### osmTGmod

osmTGmod is a load-flow model of the German transmission-grid, based on the free geo-database OpenStreetMap (OSM)

https://github.com/openego
https://github.com/openego/osmTGmod


# Inputdaten und Synthese von Zeitreihen

### Repräsentative elektrische Lastprofile für Einfamilienhäuser in Deutschland auf 1-sekündiger Datenbasis.

Quelle: HTW Berlin
Lizenz :CC-BY-NC-4.0
DOI: 10.13140/RG.2.1.5112.0080/1


### Open Energy Platform

Sammlung vieler Datensätze. Auch Zeitreihen für Erzeuger und Lasten (z.B. 1h-Auflösung)
Lizenz: Abhängig vom Datensatz - offen
http://oep.iks.cs.ovgu.de/



### DemandRegio disaggregator

Bedarfszeitreihen für Industrie und GHD (auch Haushalte) aus dem DemandRegio disaggregator
Quelle: Projekt DemandRegio: 
Lizenz: GPLv3

https://github.com/DemandRegioTeam/disaggregator

### DWD

Wetterdatensätze des DWD
Tip: Lücken füllen mit Daten ähnlicher TRY-Tage
Beschreibung des Datensatzes: https://opendata.dwd.de/climate_environment/CDC/Liesmich_intro_CDC-FTP.pdf
Lizenz/ Nutzungsbedingung: https://opendata.dwd.de/climate_environment/CDC/Nutzungsbedingungen_German.pdf
Daten frei verfügbar, Nutzung mit Quellangabe
Downloadbereich: https://www.dwd.de/DE/leistungen/cdc/climate-data-center.html;jsessionid=64E75E2FF1A46D192C61C9DF50F2E1AB.live11043?nn=17626

### BNetzA/SMARD

SMARD Strommarktdaten der Bundesnetzagentur,
Historische Strompreiszeitreihen (Day-Ahead) 
Lizenz: CC BY 4.0
https://www.smard.de/home

### FfE OpenData Seite

Zeitreihen zu Last, Erzeugung, CO2
Herkunft: Verschiedene FfE-Projekte: 
Achtung: Sehr umfangreiche Abfragen via REST nur eingeschränkt möglich. Bei umfangreichen Abfragen Kontakt per E-Mail herstellen
Lizenzen: Abhängig vom Datensatz (Quellen der Eingangsdaten), meist CC-BY 4.0

http://opendata.ffe.de/


### WDC Climate Reanalyse-Wetterzeitreihen
Reanalyse-Wetterzeitreihen
Lizenz: CC-BY 2.0

https://cera-www.dkrz.de/WDCC/ui/cerasearch/q?page=45&query=coastdat-2+cosmo-clm&rows=15

### Uni Hannover Synthetische Haushaltslastprofile

Synthetische Haushaltslastprofile
Lizenz: CC-BY 3.0

https://data.uni-hannover.de/dataset/ml_household_end-use_load-profiles

### powerplantmatching

Vergleich und Bewertung verschiedener kommerzieller und nicht kommerzieller Datenbanken zu Kraftwerkslisten.
Achtung: Nicht alle Befehle im Beispiel Jupyter Notebooks funktionieren
Lizenz: GNU General Public License v3.0

https://github.com/FRESNA/powerplantmatching

### Hydropower modelling data
Hydropower modelling data
Herkunft: ENTSO-E + Aufbereitung
Lizenz: CC 4.0

https://zenodo.org/record/3985078#.YDZpGHkxn-h

### EMHIRES

EMHIRES: Kapazitätsfaktoren für Wind und PV. Verfügbar auf NUTS2-Ebene
Lizenz: unbekannt

Wind: https://op.europa.eu/en/publication-detail/-/publication/85b2dc7f-aa61-11e6-aab7-01aa75ed71a1/language-en
PV: https://publications.jrc.ec.europa.eu/repository/handle/JRC106897


### ENTSO-e Klima-Datenbank

ENTSO-e Klima-Datenbank für Mid-term adequacy report
Lizenz: unbekannt

https://www.entsoe.eu/outlooks/midterm/#download

### Open-Power-System-Data

Content: 
- List of conventional power plants in Germany and European countries 
- Aggregated generation capacity by technology and country
- List of renewable energy power stations
- Load, wind and solar, prices in hourly resolution
- Hourly geographically aggregated weather data for Europe
- Detailed household load and solar generation in minutely to hourly resolution
- Renewables.ninja PV and Wind Profiles 	
- When2Heat Heating Profiles: Simulated hourly country-aggregated heat demand and COP time series

Achtung: Historische EE-Einspeisung nach Curtailment -> unterschätzt Verfügbarkeit 
Lizenz: Nicht einheitlich (Lizenz der Inputdaten)
https://open-power-system-data.org/

### Pypsa-EUr
Trägt Daten aus verschiedenen Quellen zusammen
Lizenz: Data files are licensed under CC-BY-4.0.
https://github.com/PyPSA/pypsa-eur

### ENTSO-E Transparency Platform

ENTSO-E Transparency Platform
Achtung: Teilweise fehlende Stunden oder Tagen
Lizenzen: Abhängig vom Datensatz - offen
https://transparency.entsoe.eu/

FTP Client nutzen (z.B. FileZilla) und Anleitung nutzen (https://transparency.entsoe.eu/content/static_content/Static%20content/web%20api/Guide.html) - für große Datenmengen
Alternativ entsoe-py (https://github.com/EnergieID/entsoe-py) - klappt aber noch nicht mit allen Datensätzen


### Pecan Street Inc.
Pecan Street Inc. Datensatz für Lastprognosen
Herkunft: USA (Texas, NY, California)
Lizenzen: Kleiner Teil ist frei zugänglich für Universitäten, sonst über Lizenzen
https://www.pecanstreet.org/dataport/

### Öko-Institut
Generische EE-Strom-Einspeisezeitreihen mit unterschiedlichem Grad an fluktuierendem Stromangebot
Lizenz: Creative Commons Namensnennung, Weitergabe unter gleichen Bedingungen 3.0 Lizenz (CC-BY-SA 3.0)
https://www.oeko.de/publikationen/p-details/erstellung-generischer-ee-strom-einspeisezeitreihen-mit-unterschiedlichem-grad-an-fluktuierendem-str

### Renewable.ninja
PV- und Wind-Zeitreihen von Renewable.ninja
Creative Commons Attribution-NonCommercial
https://www.renewables.ninja/


### feedinlib
The feedinlib is a tool to calculate feed-in time series of photovoltaic and wind power plants. It therefore provides interfaces between different weather data sets and feed-in models. It is part of the oemof group but works as a standalone application.
Lizenz: MIT License
https://github.com/oemof/feedinlib


# Beschreibung von Zeitreihen / Metadaten 

Zeitreihen müssen immer irgendwie beschrieben werden. Dieser Abschnitt soll einige Denkanstöße geben, welche Metadaten-Felder relevant sein könnten, wie man die Daten am besten mit den Metadaten zusammen speichern könnte und wo typische Fallstricke lauern.

### Typische Felder in den Metadaten

Dieser Abschnitt soll als Inspiration dienen, wenn man seine eigenen Zeitreihen beschreiben möchte. Es ist lohnenswert, über folgende Felder nachzudenken:

- Inhalt des Datensatzes. Was beschreibt die Zeitreihe?
- Zeitraum
- Auflösung
- Standort
- Regionaler Bezug
- Relative Zeitbezüge (Typwochen) vs. absolute Zeitpunkt mit eigenem Marker
- Wenn Zeiträume angegeben sind: Definition, worauf sich der Zeitstempel bezieht (Anfang, Mitte, Ende des Intervalls)
- Wie wurde sie gewonnen? Synthetisch? Gemessen?
- Einschätzung wie repräsentativ die Zeitreihe ist? Qualitätseinschätzung? 
- Beschreibung der Gradienten in den Zeitreihen?
- Welche Prozessierungsschritte hat die Zeitreihe durchlaufen?
- Zeitpunkt der Datenerfassung oder -updates
- Zeitliche Auflösung, bspw. stündliche Auflösung
- Einheiten (MW, kW,..)
- Wertebereiche
- Art der Erfassung: Mittelwert, Max, Min, Median (z.B. bei Angabe von Stundenwerten)
- Variabilität: ein meteorologisches Jahr (Jahres-, Monats-, Tagessummen, etc.)
- Bei synthetischen Daten: wie viel Trainingsdaten?
- Sub-Quellen
- Bei Leistungszeitreihen: Primärenergie, End-, ... bzw. Bezugspunkt
- Ganz Wichtig! Lizenz

### Speicherung von Metadaten

Eins der Probleme mit den Metadaten ist, dass die eigentlichen Daten zusammen mit den Metadaten abgelegt werden müssen.
Hier sind einige Ideen, wie das erfolgen kann:

- Datenbanken, jeweils eine Daten-Tabelle und eine Metadaten-Tabelle
- Git Abhängigkeiten
- Git-Lösung + Zenodo DOI
- Beschreibung der Daten in einer Wiki
- Beschreibungsdatei
- Kombination aus Metafile und Datendatei in ZIP
- Zeitreihen auf OEP veröffentlicht und dann dort geforderte Metadaten ausfüllen
- Kommentiertes Jupyter Notebook, insbesondere für Output-Daten
- RDF-Standard
- HDF5-Dateien mit Metadaten an jeder Tabelle

### Metadaten-Standards

Es gibt eine Reihe von Standards für Metadaten. Hier sind einige Links:

- Dublin-Core
- https://github.com/OpenEnergyPlatform/oemetadata, JSON-string 
- Aktuelle Entwicklung: Open Energy Ontology https://openenergy-platform.org/ontology/
- https://specs.frictionlessdata.io/

### Probleme bei Metadaten

Hier ist eine Liste von typischen Problemen bei Metadaten. Das soll als Hinweis dienen, worauf zu achten ist:

- Interpretierbarkeit von Daten
- Verständlichkeit der Kürzel
- Es ist häufig ein Konflikt zwischen einer Optimierung für Menschenlesbarkeit und Maschinenlesbarkeit vorhanden
- Kuration nur durch einige wenige Experten, die alles Wissen sammeln.
- Lizenzen müssen spezifiziert sein, insbes. bei Open Data Anspruch
- Datenbezeichnung nicht eindeutig oder nur im Vergleich zu anderen Daten im Datensatz. Beispiele könnten helfen oder bei ähnlichen Einträgen eine Erklärung des Unterschieds
- Diskrepanzen zwischen verschiedenen Plattformen
- Fachgebietswechsel möglich zwischen Datensatz-Ersteller und Datensatz-Verwender, Benennung sollte das berücksichtigen



# Herausforderungen und Lücken bei Zeitreihen

Dieser Abschnitt ist möglicherweise der wichtigste im Dokument: Er hilft dabei, nicht sinnlos Zeit zu verschwenden auf der Suche nach Daten, die es nicht gibt.

## Herausforderungen bei den Zeitreihen

- Datenumfang (ENTSO-E Daten, mehrere Jahre, Erzeugung pro Kraftwerk)
- Datenlücken (z.B. bei ENTSO-E oder bei Wetterdaten von Messstationen)
- Einheitliche Zeitstempel (+1 vs +2) - UTC vs. CE(S)Time, außerdem wird unterschiedlich gehandhabt, ob der Anfang des Zeitintervalls angegeben wird, oder das Ende (besonders 24 vs 0 Uhr)
- Zusammenfügen großer Mengen an Daten, viele Datasets
- Zeitreihen für Prozesswärme
- Fehlender Arbeitsspeicher bei großen Dataframes
- Unterschiedliche Zeichensätze (UTF-8 etc.)
- keine einheitliche Datenkonsistenz (unterschiedliche Annahmen / Szenariorahmen) bei Verwendung aus verschiedenen Quellen - keine einheitliche Datenkonsistenz
- Messfehler 

## Lücken in der Datenverfügbarkeit für unsere Domäne

Teilweise Verfügbar:
- Langjährige Wetterdaten (20+ a)
- zeitlich aufgelöste industrielle Lastprofile
- Wartungs- und Revisionsarbeiten an Kraftwerken
- EE-Verfügbarkeiten ausdifferenziert nach verschiedenen Technologien dergleichen EE-Kategorie (z.B. verschiedene PV-Technologien)
- Brennstoff-/ Rohstoffverfügbarkeit national
- ökonomische Daten (Investitionen, flexible Kosten)

Absolut nicht verfügbar:
- Standortscharfe Industrielasten
- detaillierte, gemessene Mobilitätsdaten (Synthese möglich über verschiedene Tools wie z.B. emobpy, s.o.)
- zukünftiger Netzausbau bis 2050
- Reservoir+Run-of-River Zeitreihen für alle europäischen Länder 
- Power-to-Gas Standorte inkl. technischer Daten, sowie Zukunftsszenarien
