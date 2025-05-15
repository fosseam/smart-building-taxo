# Smart Building & Sektorenkopplung

## Taxonomie für innovative Gebäudeautomatisierung, Haustechnik und Sektorenkopplung

Dieses Repository enthält eine offene Taxonomie zur Klassifizierung von Produkten, Konzepten und Technologien im Bereich innovativer Gebäudeautomatisierung, Haustechnik und Sektorenkopplung. Das Ziel ist die Schaffung einer gemeinsamen Struktur und Terminologie, die für Produktkataloge, Wissensdatenbanken, Forschung und die allgemeine Orientierung in diesem komplexen Feld genutzt werden kann.

## Motivation

Die Energiewende erfordert die intelligente Vernetzung der Sektoren Strom, Wärme und Mobilität. Innovative Haustechnik spielt dabei eine zentrale Rolle. Die Vielfalt der Technologien, Konzepte (von P2X über V2G bis hin zu Abwärmenutzung) und Automatisierungslösungen wächst rasant. Eine klare, offene und maschinenlesbare Struktur (Taxonomie) hilft dabei, den Überblick zu behalten, Produkte zu finden, Systemzusammenhänge zu verstehen und die Kommunikation in diesem Feld zu verbessern.

Diese Taxonomie hat einen besonderen Fokus auf Lösungen, die zur **Dekarbonisierung** der Hauptsektoren beitragen und **Kreislaufwirtschafts-Prinzipien** berücksichtigen ("Re:Thinking").

## Struktur der Taxonomie

Die Taxonomie ist in drei separate, verknüpfte JSON-Dateien unterteilt:

1.  **`sector-tree.json`**: Klassifiziert Produkte und Systeme nach ihrer primären **Funktion oder Rolle** in einem traditionellen Energiesystem (Erzeugung, Speicher, Verbraucher, Umwandlung, Management, Kommunikation, Monitoring).
2.  **`coupling-tree.json`**: Klassifiziert **Konzepte und Technologien** basierend auf den **Schnittstellen und Mechanismen** der Sektorenkopplung (z.B. Power-to-Heat, Vehicle-to-Grid, Abwärmenutzung, Systemintegration). Fokussiert auf die Verbindung der Sektoren.
3.  **`rethink-tree.json`**: Klassifiziert **Konzepte und Prinzipien** aus Sicht der **Kreislaufwirtschaft und Effizienz** (z.B. Bidirektionale Flüsse, Abfall-/Sekundärnutzung, Produktlebenszyklus, Reduzieren & Effizienz). Fokussiert auf nachhaltige und ressourcenschonende Aspekte.

Zusätzlich wird in Zukunft eine `products.json` aufgebaut, den wir zusammen pflegen können.

### JSON-Struktur

Jeder Knoten in den `*-tree.json` Dateien ist ein JSON-Objekt mit folgenden Attributen:

*   `pos` (String): Die Position des Knotens in der Hierarchie (z.B. "1.2.3"). Dient der Sortierung und visuellen Darstellung.
*   `id` (String): Eine eindeutige, stabile ID für den Knoten (Kleinschreibung mit Bindestrich, z.B. "sc-p2h"). Wird für Referenzen aus der `products.json` verwendet.
*   `name` (String): Der für Benutzer sichtbare Name des Knotens.
*   `description` (String): Eine kurze Beschreibung des Konzepts oder der Kategorie.
*   `nodes` (Array): Ein Array von Kind-Knoten (Objekte desselben Typs). Ein leeres Array `[]` oder fehlendes Attribut zeigt einen Blattknoten an.

### Visualisierung (ASCII Trees)

Um die Struktur der Taxonomien besser zu überblicken, werden hier die ASCII-Baumansichten der JSON-Dateien bereitgestellt.

#### sector-tree

```
├── 1: Energieerzeugung
│   ├── 1.1: Stromerzeugung
│   │   ├── 1.1.1: Photovoltaik
│   │   ├── 1.1.2: Kleinwindanlagen
│   │   └── 1.1.3: Biomasse & Abfall (Strom)
│   └── 1.2: Wärmeerzeugung
│       ├── 1.2.1: Solarthermie
│       ├── 1.2.2: Wärmepumpen
│       │   ├── 1.2.2.1: Luft/Wasser Wärmepumpen
│       │   └── 1.2.2.2: Sole/Wasser Wärmepumpen
│       ├── 1.2.3: Heizkessel
│       └── 1.2.4: Wärme aus Abfall/Sek.
├── 2: Energiespeicherung
│   ├── 2.1: Stromspeicher
│   │   └── 2.1.1: Batteriespeicher
│   │       ├── 2.1.1.1: Lithium-Ionen Batterien
│   │       ├── 2.1.1.2: Redox-Flow Batterien
│   │       └── 2.1.1.3: Blei-Säure Batterien
│   └── 2.2: Wärme- & Kältespeicher
│       ├── 2.2.1: Wärmespeicher
│       └── 2.2.2: Kältespeicher
├── 3: Energieverbraucher & Endgeräte
│   ├── 3.1: Raumklima (Heizen, Kühlen, Lüften)
│   │   ├── 3.1.1: Wärme-/Kälteabgabe
│   │   ├── 3.1.2: Verteilungssysteme Klima
│   │   ├── 3.1.3: Lüftungssysteme
│   │   └── 3.1.4: Klimatisierung
│   ├── 3.2: Elektromobilität
│   │   ├── 3.2.1: AC Ladestationen
│   │   ├── 3.2.2: DC Ladestationen
│   │   ├── 3.2.3: Swapping Stationen
│   │   └── 3.2.4: Induktives Laden
│   ├── 3.3: Steuerbare elektrische Lasten
│   │   ├── 3.3.1: Smarte Steckdosen/Schalter
│   │   ├── 3.3.2: Smarte Haushaltsgeräte
│   │   └── 3.3.3: Industrielle Lasten
│   └── 3.4: Beleuchtung
│       ├── 3.4.1: Beleuchtungssysteme
│       └── 3.4.2: Steuerbare Leuchten/Module
├── 4: Energie-Umwandlung & -Verteilung
│   ├── 4.1: Wechselrichter & Laderegler
│   │   ├── 4.1.1: PV-Wechselrichter
│   │   ├── 4.1.2: Batterie-Wechselrichter
│   │   ├── 4.1.3: Hybrid-Wechselrichter
│   │   └── 4.1.4: Laderegler
│   ├── 4.2: Transformatoren & DC/DC-Wandler
│   │   ├── 4.2.1: Transformatoren
│   │   └── 4.2.2: DC/DC-Wandler
│   ├── 4.3: Verteilsysteme & Übergabe
│   │   ├── 4.3.1: Elektrische Verteilung
│   │   └── 4.3.2: Thermische Verteilung
│   └── 4.4: Systeme zur Wärmerückgewinnung
│       ├── 4.4.1: Wärmetauscher
│       └── 4.4.2: Integrationsmodule Abwärme
├── 5: Management-, Steuerungs- & Automatisierungssysteme
│   ├── 5.1: Plattformen & Zentralen
│   │   ├── 5.1.1: Home Automation Plattformen (Matter)
│   │   ├── 5.1.2: Energie-Management Systeme (EMS)
│   │   ├── 5.1.3: Building Management Systems (BMS)
│   │   └── 5.1.4: Industrieautomatisierung (MES/SCADA)
│   ├── 5.2: Steuerungsmodule & Gateways
│   │   ├── 5.2.1: Logik-Controller (PLCs/Industrie PCs)
│   │   ├── 5.2.2: I/O-Module
│   │   └── 5.2.3: Protokoll-Gateways
│   ├── 5.3: Sensorik
│   │   ├── 5.3.1: Elektrische Sensorik
│   │   ├── 5.3.2: Thermische Sensorik
│   │   ├── 5.3.3: Umweltsensorik
│   │   ├── 5.3.4: Präsenz- & Bewegungssensorik
│   │   └── 5.3.5: Physikalische Sensorik
│   └── 5.4: Aktorik
│       ├── 5.4.1: Schaltaktoren
│       ├── 5.4.2: Dimmaktoren
│       ├── 5.4.3: Ventilaktoren
│       └── 5.4.4: Motoraktoren
├── 6: Kommunikation & Infrastruktur
│   ├── 6.1: Kabelgebundene Kommunikation
│   │   ├── 6.1.1: Ethernet / IP-basiert
│   │   ├── 6.1.2: Feldbus-Systeme
│   │   └── 6.1.3: M-Bus
│   ├── 6.2: Funkkommunikation
│   │   ├── 6.2.1: Kurzreichweite (Inhouse)
│   │   ├── 6.2.2: Langreichweite (LPWAN/Mobilfunk)
│   │   └── 6.2.3: Spezifische Funkprotokolle
│   ├── 6.3: Netzwerk-Gateways & Router
│   │   ├── 6.3.1: Gateways
│   │   └── 6.3.2: Router & Switche
│   └── 6.4: Datenlogger
│       ├── 6.4.1: Energie
│       ├── 6.4.2: Gas & Wasser
│       ├── 6.4.3: Umwelt
│       └── 6.4.4: System
└── 7: Monitoring, Analyse & Software
    ├── 7.1: Software & Plattformen (Monitoring/Analyse)
    │   ├── 7.1.1: Monitoring Software/Plattformen
    │   ├── 7.1.2: Analyse Software/Plattformen
    │   └── 7.1.3: Visualisierungs-Tools
    └── 7.2: Zähler & Messtechnik (Hardware)
        ├── 7.2.1: Stromzähler
        ├── 7.2.2: Wärme-/Kältemengenzähler
        └── 7.2.3: Gas- & Wasserzähler

```


#### coupling-tree

└── 1: Sektorenkopplungskonzepte
    ├── 1.1: Strom-Kopplungskonzepte
    │   ├── 1.1.1: Power-to-X Umwandlungen (P2X)
    │   │   ├── 1.1.1.1: Power-to-Heat (P2H)
    │   │   ├── 1.1.1.2: Power-to-Gas (P2G)
    │   │   ├── 1.1.1.3: Power-to-Liquid (P2L)
    │   │   └── 1.1.1.4: Power-to-Chemicals (P2C)
    │   ├── 1.1.2: Elektrische Speicher (P2P)
    │   │   ├── 1.1.2.1: Batteriespeicher
    │   │   ├── 1.1.2.2: Gravity-Speicher
    │   │   ├── 1.1.2.3: Pumpspeicher
    │   │   ├── 1.1.2.4: Druckluftspeicher (CAES)
    │   │   ├── 1.1.2.5: Schwungmassenspeicher
    │   │   └── 1.1.2.6: Weitere elektrische Speicher
    │   ├── 1.1.3: X-to-Power Umwandlungen (X2P)
    │   │   ├── 1.1.3.1: Heat-to-Power (H2P)
    │   │   └── 1.1.3.2: Gas-to-Power (G2P)
    │   └── 1.1.4: Elektrische Flexibilität
    │       ├── 1.1.4.1: Lastmanagement (elektrisch)
    │       └── 1.1.4.2: Speicherflexibilität (elektrisch)
    ├── 1.2: Thermische Kopplungskonzepte
    │   ├── 1.2.1: Power-to-Heat (P2H)
    │   ├── 1.2.2: Heat-to-Cool (H2C)
    │   ├── 1.2.3: Gas-to-Heat (G2H)
    │   ├── 1.2.4: Nutzung thermischer Energiequellen
    │   │   ├── 1.2.4.1: Abwärmekopplung
    │   │   ├── 1.2.4.2: Solarthermie-Kopplung
    │   │   └── 1.2.4.3: Geothermie-Kopplung
    │   └── 1.2.5: Thermische Speicher-Kopplung
    ├── 1.3: Mobilitäts-Kopplungskonzepte
    │   ├── 1.3.1: Grid-to-Vehicle (G2V) Strategien
    │   │   ├── 1.3.1.1: Kabelgebundenes Laden (G2V)
    │   │   ├── 1.3.1.2: Induktives Laden (G2V)
    │   │   └── 1.3.1.3: Battery Swapping (G2V-Basis)
    │   ├── 1.3.2: Vehicle-to-X (V2X)
    │   │   ├── 1.3.2.1: Vehicle-to-Grid (V2G)
    │   │   ├── 1.3.2.2: Vehicle-to-Home (V2H)
    │   │   └── 1.3.2.3: Vehicle-to-Load (V2L)
    │   └── 1.3.3: Alternative Kraftstoffe für Mobilität
    │       ├── 1.3.3.1: Wasserstoff (H2)
    │       ├── 1.3.3.2: Methan / Biomethan
    │       └── 1.3.3.3: E-Fuels / Syn-Fuels
    └── 1.4: Sektorenübergreifende Systemintegration & Flexibilität
        ├── 1.4.1: Sektorenübergreifendes Energiemanagement
        ├── 1.4.2: Quartiers- & Areal-Kopplung
        ├── 1.4.3: Marktintegration & Geschäftsmodelle
        ├── 1.4.4: Systemische Flexibilitätskonzepte
        └── 1.4.5: Netzinteraktion (Strom-, Wärme-, Gasnetz)

#### rethink-tree







## Nutzung der Taxonomie

Die JSON-Dateien können direkt in Anwendungen (z.B. für Produktfilter, Navigationsmenüs) oder als Grundlage für weitere Analysen und Visualisierungen verwendet werden. Die `id` dient als stabile Referenz, die `pos` zur hierarchischen Anzeige.

## Zitieren

Dieses Repository ist mit Zenodo.org integriert, um langfristige Archivierung und Zitierbarkeit sicherzustellen. Jedes Release des Repositories erhält einen eigenen DOI.

Bitte zitiere die Taxonomie unter Verwendung des DOI, wenn du sie in Publikationen, Software oder anderen Werken nutzt.

Aktueller DOI: [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.xyz)](https://doi.org/10.5281/zenodo.xyz)
*(Hinweis: Denke daran, den Platzhalter für den DOI und das Badge durch die von Zenodo bereitgestellten Werte zu ersetzen, nachdem du das erste Release erstellt hast.)*

## Lizenz

Dieses Projekt ist unter der **Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)** Lizenz lizenziert. Details dazu findest du in der [LICENSE.md](LICENSE.md) Datei.