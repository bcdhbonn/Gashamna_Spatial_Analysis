# Multi-Site Proposal Concept: Comparative Spatial Zooarchaeology & Historical Text Mining Across 5 Arctic Whaling & Trapping Sites (Svalbard, 17th–19th c.)

**To:** Colleagues in Zooarchaeology & Faunal Analysis  
**From:** Spatial Archaeology & Computational Humanities Team  
**Subject:** Multi-Site Grant Proposal Concept (Arctic Historical Ecology, Spatial Data Science & Text Mining)  
**Date:** July 24, 2026  

---

## 1. Executive Summary & Scientific Objectives

Whaling and resource exploitation in 17th–19th century Svalbard represented the first globalized, industrial-scale extraction of marine mammals in the High Arctic. While individual sites—most notably **Smeerenburg**—have been excavated in isolation, a systematic, cross-site comparative synthesis integrating **micro-spatial zooarchaeology (GIS/DBSCAN/HexBin), faunal element analysis, and automated NLP text-mining of historical archives** has never been realized.

This proposal expands our analytical pipeline from a single-site pilot to a **comparative network of 5 key Arctic shore stations across Svalbard**. By combining zooarchaeological assemblages with 400 years of historical text mining (logbooks, state papers, Sir Martin Conway 1906, and the Dutch *Smeerenburg Project* archives), we seek to model the **Historical Ecology of the High Arctic (1600–1900)**.

---

## 2. The 5 Comparative Key Sites

```
               [ NW Svalbard Cluster ]
  1. Smeerenburg (Amsterdamøya) ── 2. Ytre Norskøya ── 3. Kobbefjorden (Danskøya)
                                    │
                                    ▼
               [ South / West Fjord Cluster ]
  4. Lægerneset (Recherche Fjord) ── 5. Gåshamna (Hornsund)
```

| Site | Location | Historical Akteure / Primary Use | Zooarchaeological & Structural Signature | Key Reference / Data Basis |
| :--- | :--- | :--- | :--- | :--- |
| **1. Smeerenburg** | Amsterdamøya (NW Spitsbergen) | Dutch *Noordsche Compagnie* main HQ (1614–1660s) | 16-17 tryworks, cookeries, smithies, dwellings, extensive faunal middens (whales, walruses, seals, birds). | Groningen Arctic Centre (Louwrens Hacquebord et al.) |
| **2. Gåshamna** | Hornsund (South Spitsbergen) | English (*Muscovy Co.*), Dutch (*Zeeland*), Pomors, Norwegian Trappers | 6 trywork furnaces, dwelling foundations, mixed whale/walrus/polar bear fauna. High-res spatial point data (1994 survey). | BCDH Spatial Dataset ([`GAS_Hex_Density.ipynb`](file:///c:/Users/langm/sciebo/BCDH_Projektbox/1_BCDH%20Intern/Scripts/Gashamna/Gashamna_Spatial_Analysis-1/GAS_Hex_Density.ipynb)) |
| **3. Lægerneset** | Recherche Fjord (Bell Sound) | English (*Muscovy Company*) principal southern base | Massive trywork complexes, housing structures, graves, rich faunal deposits. | Sysselmesteren & NIKU survey archives |
| **4. Ytre Norskøya** | NW Spitsbergen | Dutch (*Zeeland Chamber*) major whaling station | 9 tryworks, 165+ graves, rich organic middens, seal/walrus/whale bone assemblages. | Hacquebord & Maat osteological studies |
| **5. Kobbefjorden / Cape Linné** | Danskøya / Isfjorden | Mixed Whaling & Russian Pomor wintering station (18th–19th c.) | Transition from commercial whaling to multi-year Pomor trapping (walrus, fox, reindeer, bear fauna). | Russian-Norwegian expedition archives |

---

## 3. Comparative Zooarchaeological Core Hypotheses

By contrasting these 5 sites across geographically distinct micro-climates (North-West vs. South-West Spitsbergen) and national operations (Dutch vs. English vs. Russian Pomor), we address four major research questions:

### A. The Smeerenburg Benchmark: Industrial Center vs. Outpost Dynamics
* **Hypothesis 1:** Smeerenburg operated as a highly specialized, mono-functional industrial hub with distinct spatial segregation between rendering (*tryworks*) and domestic quarters. Smaller outposts (like Gåshamna or Kobbefjorden) exhibit opportunistic, multi-species processing (walrus/seal butchery mixed into living areas).
* **Spatial Testing:** Comparing Hexagonal Density Binning ([`GAS_Hex_Density.ipynb`](file:///c:/Users/langm/sciebo/BCDH_Projektbox/1_BCDH%20Intern/Scripts/Gashamna/Gashamna_Spatial_Analysis-1/GAS_Hex_Density.ipynb)) and DBSCAN clustering ([`GAS_DBSCAN.ipynb`](file:///c:/Users/langm/sciebo/BCDH_Projektbox/1_BCDH%20Intern/Scripts/Gashamna/Gashamna_Spatial_Analysis-1/GAS_DBSCAN.ipynb)) across all 5 sites.

### B. Sea-Ice Driven Species Shifts (Resilience & Opportunism)
* **Hypothesis 2:** During Little Ice Age cold anomalies, heavy sea-ice blocked NW harbours (Smeerenburg, Ytre Norskøya), forcing fleets southward to Bell Sound (Lægerneset) and Hornsund (Gåshamna), where whalers pivoted to **walrus (*Odobenus rosmarus*) and seal (*Phocidae*) hunting**.
* **Zooarchaeological Testing:** Cross-referencing annual sea-ice severity extracted via text-mining from 17th-century logbooks with shifts in MNI ratios (*Balaena mysticetus* vs. *Odobenus rosmarus* / *Ursus maritimus*) across the 5 sites.

### C. Fuel Utilization & Bone Taphonomy
* **Hypothesis 3:** Timber scarcity led to variable reliance on oil-rich cetacean bone as furnace fuel. Stations in southern fjords (Gåshamna/Lægerneset) with access to driftwood show lower ratios of burnt bone than heavily denuded northern stations (Smeerenburg/Ytre Norskøya).
* **Osteological Indicators:** Combustion marks, cancellous vs. compact bone element ratios, and fragment size distributions ([`GAS_Bone_Size.ipynb`](file:///c:/Users/langm/sciebo/BCDH_Projektbox/1_BCDH%20Intern/Scripts/Gashamna/Gashamna_Spatial_Analysis-1/GAS_Bone_Size.ipynb)).

### D. The Whaling-to-Trapping Transition (17th vs. 18th/19th Century)
* **Hypothesis 4:** The extinction of coastal Bowhead Whales led to a structural shift in faunal assemblages: 17th-century cetacean-dominated middens give way to 18th-century Pomor and 19th-century Norwegian trapping assemblages dominated by *Rangifer tarandus*, *Vulpes lagopus*, *Ursus maritimus*, and *Odobenus*.

---

## 4. Methodological Workflow & Interfacing

```
 [ 5-Site Osteological Catalogues ]        [ Historical Text Mining Corpus ]
  (Smeerenburg, Gåshamna, Lægerneset,       (Dutch Noordsche Co. Archives, Conway 1906,
   Ytre Norskøya, Kobbefjorden)              English State Papers, Logbooks)
              │                                             │
              └─────────────────────┬───────────────────────┘
                                    ▼
                     [ Multi-Site Spatial GIS Pipeline ]
                   (DBSCAN, HexBin Density, Topo-Surfaces)
                                    │
                                    ▼
                     [ Arctic Historical Ecology ]
                 (5-Site Comparative Spatial Synthesis)
```

1. **Text-Mining Integration:** Automated entity extraction of dates, sea-ice mentions, vessel counts, and conflict events from Dutch, English, and Scandinavian archives.
2. **Harmonized Spatial GIS:** Normalizing 3D point data and survey layers across all 5 sites using standardized CRS templates (EPSG:25833).
3. **Comparative Spatial Statistics:** Multi-site spatial point pattern analysis (Ripley's K, Hexagonal Binning, Kernel Density Difference) to evaluate spatial efficiency and taphonomic decay.

---

## 5. Consortium, Value Proposition & Grant Targets

This multi-site proposal transforms a localized study into an international, high-impact research consortium:

* **Consortium Partners:** BCDH (Spatial Data Science & Text Mining), Groningen Arctic Centre (Smeerenburg Data & Dutch Whaling History), NIKU / Sysselmesteren (Svalbard Archaeological Heritage), and leading Zooarchaeology labs.
* **Target Funding Schemes:** **ERC Synergy Grant**, **DFG Research Grant / Transregio**, or **Horizon Europe (CL2-HERITAGE)**.
* **High-Impact Outputs:** Comparative monographs, Open-Access Spatial Web-GIS for Svalbard Cultural Heritage, and high-impact papers in *Nature Ecology & Evolution*, *Journal of Archaeological Science*, and *Quaternary Science Reviews*.
