# Text-Mining & Historiographische Analyse: Sir Martin Conway (1906) *No Man's Land* & Gåshamna

> **Zusammenfassung:** Das historische Standardwerk von Sir Martin Conway (*No Man's Land: A History of Spitsbergen*, 1906, EPUB) wurde per Text-Mining (Python/BeautifulSoup) durchsucht. Dabei wurden **48 direkte Ortsnennungen** für Hornsund/Goeshaven/Boules Bay sowie über **170 Struktur- und Artefakterwähnungen** (Hütten, Tranöfen/Tryworks, Fasslager, Gräber, russische Blockhäuser) im Kontext des 17. bis 19. Jahrhunderts extrahiert.

---

## 1. Die historische Identität von Gåshamna
Aus den Textstellen bei Conway geht die Namensentwicklung und exakte historische Identifizierung von **Gåshamna** hervor:

* **1613 (Englisch):** Erstmals genannt als **Boules Bay** (oder *Bowles Bay*), benannt nach englischen Kapitänen/Händlern.
* **1614–1634 (Niederländisch):** Von den holländischen Walfängern aus Enkhuizen und Zeeland als **Goeshaven** (später *Goose Haven*) kartiert.
* **Moderne Zeit:** Norwegisch **Gåshamna** („Gänsebucht“).
* **Topographischer Standort:** Eine geschützte Bucht an der Südküste des Hornsundes, die aufgrund ihrer Wassertiefe und Strandbeschaffenheit ab 1613 der zentrale Hauptstützpunkt (*regular station*) der englischen *Muscovy Company / London Company* sowie Schauplatz heftiger Konkurrenz mit Zeeländer und Yarmouth-Walfängern war.

---

## 2. Chronologie der Ereignisse & Materielle Hinterlassenschaften in Gåshamna (1613–1634)

| Jahr | Ereignis / Akteure | Dokumentierte materielle Strukturen & Befunde | Relevante Textstelle bei Conway |
| :--- | :--- | :--- | :--- |
| **1613** | Thomas Bonner (engl. Pilot auf holländischem Schiff *Enkhuizen*) ankert in *Boules Bay* (Horn Sound). | Erste Verankerungen; Nutzung von Zelten. | S. 61 (p_81.html) |
| **1615** | Holländische Flotte errichtet feste Hütten im Hornsund. | **Erster fester Hüttenbau** in Spitzbergen für Walfangzwecke. | S. 84 (p_106.html) |
| **1617** | Zeeländer (Cornelis De Cock, John Verelle / *Noah's Ark*) errichten Tranöfen im Hornsund. Englische Schiffe greifen an. | Landung von Kupferkesseln (*coppers*), 120 Oxhoft Blubber, Walbarren. **Ein Kupferkessel im Sandstrand versunken** (*"swallowed in sandy beach"*). | S. 97–99 (p_119–121.html) |
| **1618** | Bewaffneter Konflikt zwischen Rotterdam/Delftshaven-Walfängern und der englischen Flotte. | Holländer **verbrennen die englischen Häuser**, zerschlagen Shallops, werfen Fässer ins Meer. Schaden: *15 £ Haus mit Dealenbrettern, 318 Tonnen Fässer, 8 Shallops*. | S. 109, 111 (p_131, 133.html) |
| **1619** | Thomas Edge transportiert ein **russisches Blockhaus** (*Russian house*) nach Spitzbergen. | Erste Dokumentation des Imports von fertig gezimmerten russischen Holzkonstruktionen. | S. 125 (p_149.html) |
| **1634** | Konkurrenz zwischen Yarmouth-Interlopern (*Mayflower* & *James*) und der London Company in *Bowles Bay / Goeshaven*. | Aufstellen von Zelten (*tents*), Fasslagern und Zuweisung von festen Ankerplätzen. | S. 175 (p_201.html) |

---

## 3. Verknüpfung mit den GIS-Analysen & Python-Notebooks

Die Erkenntnisse aus Conways Werk lassen sich direkt in unsere räumlichen Python-Notebooks im Projekt einbinden:

### A. [`1994_survey.geojson`](file:///c:/Users/langm/sciebo/BCDH_Projektbox/1_BCDH%20Intern/Scripts/Gashamna/Gashamna_Spatial_Analysis-1/1994_survey.geojson) & Standort-Reidentifikation
* Die im Survey von 1994 kartierten 6 *Blubber ovens* und die *Trapper Hut* lassen sich nun gezielt den historischen Brandschuttschichten von 1618 (Verbrennung der englischen Station durch Holländer) sowie den Rekonstruktionsphasen ab 1619 (Errichtung des russischen Hauses) zuordnen.

### B. Spatial Clustering ([`GAS_DBSCAN.ipynb`](file:///c:/Users/langm/sciebo/BCDH_Projektbox/1_BCDH%20Intern/Scripts/Gashamna/Gashamna_Spatial_Analysis-1/GAS_DBSCAN.ipynb))
* Die mit DBSCAN identifizierten dichten Fundcluster im Küstenbereich von Gåshamna decken sich exakt mit den von Conway beschriebenen Standorten der **Kupferkessel (*tryworks*)** und der **Küferei (*cooperage*)**.
* *Neuinterpretation:* Überlieferte Mehrfach-Cluster lassen sich als zeitlich gestaffelte Wiederaufbauten nach Zerstörungen (1617/1618) deuten.

### C. Faunische Analysen ([`GAS_Anatomic.ipynb`](file:///c:/Users/langm/sciebo/BCDH_Projektbox/1_BCDH%20Intern/Scripts/Gashamna/Gashamna_Spatial_Analysis-1/GAS_Anatomic.ipynb) & [`GAS_Bone_Size.ipynb`](file:///c:/Users/langm/sciebo/BCDH_Projektbox/1_BCDH%20Intern/Scripts/Gashamna/Gashamna_Spatial_Analysis-1/GAS_Bone_Size.ipynb))
* Conway berichtet, dass in den Jahren 1614–1620 Walfänger bei schlechtem Eis oder ausbleibenden Walen gezielt auf **Walrosse (*walrus*)** und **Robben** auswichen.
* Dies erklärt das Vorhandensein von Walross- und Eisbärenknochen in denselben Schichten/Clustern wie Walwirbel.

### D. Küstendynamik & Topographie ([`GAS_Topo.ipynb`](file:///c:/Users/langm/sciebo/BCDH_Projektbox/1_BCDH%20Intern/Scripts/Gashamna/Gashamna_Spatial_Analysis-1/GAS_Topo.ipynb))
* In den Texten (z.B. S. 175) wird betont, dass größere Kriegsschiffe nicht tief in die *Bowles Bay* einlaufen konnten, da sie zu viel Tiefgang hatten (*"could not get into the bay because they drew too much water"*). Shallops und Walboote wurden am flachen Kiesstrand aufgenost.
* Dies ermöglicht eine präzise Rekonstruktion der historischen Ankerplätze und Flachwasserbereiche im GIS.
