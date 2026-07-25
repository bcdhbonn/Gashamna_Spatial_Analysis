# Projektinitiative: Spatial Zooarchaeology & Historical Text Mining in Gåshamna (Svalbard)

**An:** Kolleginnen und Kollegen der Archäozoologie  
**Von:** Spatial Archaeology & Computational Humanities Team  
**Betreff:** Skizze für ein interdisziplinäres Forschungsprojekt (Arktische Historical Ecology, Raumanalytik & Text-Mining)  
**Datum:** 24. Juli 2026  

---

## 1. Ausgangslage & Wissenschaftliche Zielsetzung

Der arktische Fundplatz **Gåshamna (Hornsund, Svalbard)** stellt eine der bedeutendsten frühneuzeitlichen Walfang- und Trapperstationen Spitzbergens dar. Das Areal umfasst komplexe Befundstrukturen (Tranöfen/*Tryworks*, Hüttengrundrisse, Gräber) sowie umfangreiche Anhäufungen faunischer Reste. 

Bisherige archäozoologische Studien in der Arktis betrachten Knochenassemblagen häufig rein quantitativ (NSP, MNI) oder isoliert nach Fundschichten. In unserem Vorhaben möchten wir die **archäozoologische Datenbasis erstmals voll-integriert mit modernen Methoden der räumlichen Data Science (GIS, DBSCAN Clustering, Hexagonal Binning) und automatisiertem Text-Mining historischer Großkorpora** verschneiden.

Das Ziel ist die Rekonstruktion der **Historical Ecology des Hornsundes (17.–19. Jahrhundert)**: Wie wandelte sich die Ausbeutung arktischer Ressourcen (Wale, Walrosse, Eisbären, Robben, Rentiere) unter dem Druck von Klimaschwankungen (*Kleine Eiszeit*) und europäischer Marktkonkurrenz, und wie spiegelt sich dieser Prozess mikroräumlich auf dem Fundplatz wider?

---

## 2. Archäozoologische Kernfragen & Synergien

Für die Archäozoologie eröffnen sich in diesem integrierten Ansatz neuartige Forschungsfelder:

### A. Räumliche Taphonomie & Prozessketten (Flensing, Rendering, Butchery)
* **Zonierung der Verarbeitung:** Über räumliche Dichteanalysen (z. B. [`GAS_Anatomic.ipynb`](file:///c:/Users/langm/sciebo/BCDH_Projektbox/1_BCDH%20Intern/Scripts/Gashamna/Gashamna_Spatial_Analysis-1/GAS_Anatomic.ipynb)) untersuchen wir die räumliche Entkopplung von primären Zerlegungsplätzen (Uferbereich/Flensing) und sekundären Verarbeitungszonen (Tranöfen/Tryworks).
* **Fragmentierung & Knochengrößen-Cluster:** Über Algorithmen zur Knochengrößen-Verteilung ([`GAS_Bone_Size.ipynb`](file:///c:/Users/langm/sciebo/BCDH_Projektbox/1_BCDH%20Intern/Scripts/Gashamna/Gashamna_Spatial_Analysis-1/GAS_Bone_Size.ipynb)) lässt sich differenzieren, ob feingliedrige Reste (z. B. Extremitäten von Pelztieren oder Geflügel) in Wohnbereichen liegen, während schwere Walwirbel und Schädel als Baumaterial oder Heizstoff an den Öfen konzentriert sind.
* **Permafrost- & Solifluktions-Taphonomie:** Über den Abgleich mit digitalen Geländemodellen ([`GAS_Topo.ipynb`](file:///c:/Users/langm/sciebo/BCDH_Projektbox/1_BCDH%20Intern/Scripts/Gashamna/Gashamna_Spatial_Analysis-1/GAS_Topo.ipynb)) prüfen wir, wie Geomorphologie und Frostmusterböden die Lage der Osteofakte im Laufe von 400 Jahren verändert haben.

### B. Das „Resilienz- & Subsistenz-Modell“: Ausweichstrategien bei Eisdruck
* Aus von uns durchgeführten Text-Mining-Analysen (u. a. Sir Martin Conway 1906, *No Man’s Land*) geht hervor, dass in eisreichen Jahren der Walfang in den Fjorden zusammenbrach. Die Walfänger wichen in diesen Saisons gezielt auf **Walross- (*Odobenus rosmarus*) und Robbenjagd** aus.
* **Archäozoologische Evidenz:** Lassen sich im Fundgut scharf abgegrenzte Straten oder mikro-räumliche Cluster nachweisen, in denen Walross-Crania, Tusks oder Pholiden-Skelettelemente die Cetaceen-Reste dominieren? 
* Wie verändert sich das Verhältnis von *Balaena mysticetus* (Grönlandwal) zu opportunistischer Fauna über die verschiedenen Besiedlungsphasen?

### C. Skelettelement-Frequenz & Brennstoffnutzung
* Walfangstationen in Holz-armen arktischen Zonen nutzten tranreiche Walbone als Heizmaterial für die Tranöfen. 
* Über die Bestimmung des Verhältnisses von spongiösen zu kompakten Skelettelementen sowie Brandspuren an Knochen können wir die archäozoologische Debatte um die **Nutzung von Wal-Osteofakten als Brennstoff** quantitativ auf eine neue Basis stellen.

---

## 3. Die Methodik: Wie arbeiten Archäozoologie & Data Science zusammen?

```
 [ Osteologische Daten ]         [ Historische Text-Quellen ]
   (Species, NNI, Patho,           (Logbücher, Conway 1906,
    Element, Size, Burn)             NLP-Entity Extraction)
             │                                 │
             └───────────────┬─────────────────┘
                             ▼
              [ Spatial Data Science Pipeline ]
             (HexBin Density, DBSCAN, Topo-GIS)
                             │
                             ▼
              [ Historical Ecology Synthesis ]
            (Ressourcen-Abbau, Taphonomie, ABM)
```

1. **High-Resolution Spatial Mapping:** Jeder Knochenfund wird nicht nur taxonomisch und anatomisch erfasst, sondern mit präzisen XYZ-Koordinaten in das Spatial-System eingespeist.
2. **Hexagonal Density Binning:** Statt invarianter Rastersysteme nutzen wir maßstabsgetreue hexagonale Binning-Verfahren ([`GAS_Hex_Density.ipynb`](file:///c:/Users/langm/sciebo/BCDH_Projektbox/1_BCDH%20Intern/Scripts/Gashamna/Gashamna_Spatial_Analysis-1/GAS_Hex_Density.ipynb)), die dichteunabhängig art- und elementreine Verteilungsmuster sichtbar machen.
3. **Text-Mining Cross-Validation:** Historisch überlieferte Ereignisse (z. B. Zerstörung von Stationen 1618, Überwinterungen ab 1630, Pomor-Jagd im 18. Jh.) liefern zeitliche Ankerpunkte, die mit den zooarchäologischen Phasen abgeglichen werden.

---

## 4. Mehrwert für die Archäozoologie & Publikationspotenzial

Ein gemeinsamer Antrag (z. B. DFG-Sachbeihilfe, ERC Synergy oder VolkswagenStiftung) bietet hervorragende Synergien:

* **High-Impact Publikationen:** Das Projekt verbindet klassische Archäozoologie mit cutting-edge Digital Humanities und Arktisforschung (Ziel-Journale: *Journal of Archaeological Science*, *International Journal of Osteoarchaeology*, *Quaternary International*, *Polar Record*).
* **Beitrag zur Anthropozän-Debatte:** Rekonstruktion des historischen Artenschwunds in der Arktis als ökologische Baseline für moderne Biologen und Klimaforscher.
* **Rettung arktischen Kulturguts:** Durch den rasanten Klimawandel (Küstenerosion im Hornsund) sind die Knochenassemblagen in Gåshamna akut vom Verlust bedroht. Das Projekt liefert eine digitale Sicherung.

---

## 5. Nächste Schritte zur Antragsbereitung

1. **Dateninventur & Schnittstellen:** Abgleich der bestehenden osteologischen Fundkataloge von Gåshamna mit unserer GIS-Struktur.
2. **Fokus-Taxa festlegen:** Definition der Zielspezies (*Balaena mysticetus*, *Odobenus rosmarus*, *Ursus maritimus*, *Rangifer tarandus*).
3. **Pilot-Analyse:** Gemeinsame Auswertung eines Test-Sektors zur Demonstration der Visualisierungs- und Clustering-Pipeline.

Wir freuen uns darauf, diese Initiative gemeinsam mit Ihnen als Co-PIs zu gestalten!
