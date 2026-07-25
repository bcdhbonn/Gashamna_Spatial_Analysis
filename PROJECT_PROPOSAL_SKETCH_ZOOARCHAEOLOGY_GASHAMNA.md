# Project Proposal Concept: Spatial Zooarchaeology & Historical Text Mining at Gåshamna (Svalbard)

**To:** Colleagues in Zooarchaeology / Faunal Analysis  
**From:** Spatial Archaeology & Computational Humanities Team  
**Subject:** Proposal Concept for an Interdisciplinary Research Initiative (Arctic Historical Ecology, Spatial Data Science & Text Mining)  
**Date:** July 24, 2026  

---

## 1. Background & Scientific Objectives

The Arctic site **Gåshamna (Hornsund, Svalbard)** represents one of the most significant early modern whaling and trapping shore stations in Spitsbergen. The site encompasses complex structural features (blubber ovens/*tryworks*, dwelling foundations, graves) alongside extensive surface and subsurface faunal bone accumulations.

Traditional zooarchaeological studies in polar contexts often analyze faunal assemblages strictly quantitatively (NSP, MNI) or isolated by stratigraphical layers. In this initiative, we aim to **fully integrate zooarchaeological datasets with modern spatial data science (GIS, DBSCAN Clustering, Hexagonal Density Binning) and automated NLP text-mining of historical archives**.

The overarching goal is to reconstruct the **Historical Ecology of Hornsund (17th–19th century)**: How did the exploitation of Arctic marine and terrestrial fauna (*Balaena mysticetus*, *Odobenus rosmarus*, *Ursus maritimus*, *Phocidae*, *Rangifer tarandus*) shift under the dual pressures of climatic volatility (*Little Ice Age*) and European commercial competition, and how is this ecological transition expressed micro-spatially across the site?

---

## 2. Core Zooarchaeology Research Questions & Synergies

This integrated approach opens pioneering avenues for zooarchaeological inquiry:

### A. Spatial Taphonomy & Processing Chains (Flensing, Rendering, Butchery)
* **Zoning of Processing:** Using spatial density modeling (e.g., [`GAS_Anatomic.ipynb`](file:///c:/Users/langm/sciebo/BCDH_Projektbox/1_BCDH%20Intern/Scripts/Gashamna/Gashamna_Spatial_Analysis-1/GAS_Anatomic.ipynb)), we investigate spatial decoupling between primary butchery zones (coastal flensing sites) and secondary processing centers (blubber tryworks).
* **Fragmentation & Bone Size Clustering:** By applying spatial bone size distribution algorithms ([`GAS_Bone_Size.ipynb`](file:///c:/Users/langm/sciebo/BCDH_Projektbox/1_BCDH%20Intern/Scripts/Gashamna/Gashamna_Spatial_Analysis-1/GAS_Bone_Size.ipynb)), we differentiate whether small, fragile elements (e.g., fur-bearer or bird limbs) concentrate near dwelling areas, while heavy whale vertebrae and cranial fragments are aggregated at tryworks as structural material or fuel.
* **Permafrost & Solifluction Taphonomy:** Correlating bone positions with high-resolution digital elevation models ([`GAS_Topo.ipynb`](file:///c:/Users/langm/sciebo/BCDH_Projektbox/1_BCDH%20Intern/Scripts/Gashamna/Gashamna_Spatial_Analysis-1/GAS_Topo.ipynb)) allows us to model post-depositional freeze-thaw and slope movement over 400 years.

### B. Resilience & Subsistence Models: Opportunistic Species Shifts
* Automated text mining of historical accounts (e.g., Sir Martin Conway 1906, *No Man’s Land*) reveals that severe sea-ice seasons frequently collapsed fjord whaling operations. In response, whalers opportunistically pivoted to **walrus (*Odobenus rosmarus*) and seal hunting**.
* **Zooarchaeological Testing:** Can we identify spatially or stratigraphically discrete clusters where walrus cranial elements, tusks, or seal bones dominate over cetacean remains?
* How does the ratio of *Balaena mysticetus* (Bowhead Whale) to opportunistic game evolve across English, Dutch, and Russian Pomor occupation phases?

### C. Skeletal Element Frequency & Fuel Utilization
* Whaling stations in timber-scarce Arctic environments frequently burned oil-rich cetacean bone as fuel for trywork furnaces.
* Quantifying ratios of cancellous vs. compact bone elements alongside bone burning patterns allows us to re-evaluate the **whale bone fuel debate** with robust spatial statistics.

---

## 3. Methodology: Interfacing Zooarchaeology & Spatial Data Science

```
 [ Zooarchaeological Data ]        [ Historical Text Corpus ]
   (Taxa, Element, MNI,             (Logbooks, Conway 1906,
    Size, Burning, Cut-marks)         NLP Entity Mining)
              │                              │
              └──────────────┬───────────────┘
                             ▼
             [ Spatial Data Science Pipeline ]
            (HexBin Density, DBSCAN, Topo-GIS)
                             │
                             ▼
             [ Historical Ecology Synthesis ]
           (Resource Depletion, Taphonomy, ABM)
```

1. **High-Resolution Spatial Mapping:** Every faunal specimen is georeferenced with precise 3D coordinates ($X, Y, Z$) directly linking to osteological catalog attributes.
2. **Hexagonal Density Binning:** Replacing arbitrary spatial grids with fixed-extent hexagonal binning ([`GAS_Hex_Density.ipynb`](file:///c:/Users/langm/sciebo/BCDH_Projektbox/1_BCDH%20Intern/Scripts/Gashamna/Gashamna_Spatial_Analysis-1/GAS_Hex_Density.ipynb)) neutralizes spatial sampling bias and resolves species-specific hotspots.
3. **Text-Mining Validation:** Historical events (e.g., documented station destruction in 1618, overwintering camps from 1630, 18th-century Pomor hunting) serve as chronological anchors to cross-validate zooarchaeological horizons.

---

## 4. Value Proposition & Publication Strategy

A joint grant proposal (e.g., DFG Research Grant, ERC Synergy/Consolidator, or Horizon Europe) offers exceptional strategic benefits:

* **High-Impact Publications:** Positioning joint research at the intersection of zooarchaeology, digital humanities, and polar studies (*Journal of Archaeological Science*, *International Journal of Osteoarchaeology*, *Quaternary International*, *Polar Record*).
* **Anthropocene Baseline Contribution:** Establishing an empirical historical baseline for Arctic biodiversity decline and marine mammal exploitation.
* **Rescue Archaeology & Climate Risk:** Coastal erosion and permafrost thawing in Hornsund jeopardize faunal remains; this project provides a vital digital rescue record.

---

## 5. Proposed Next Steps for Grant Preparation

1. **Dataset Harmonization:** Interfacing existing Gåshamna osteological catalogues with our spatial GIS database.
2. **Target Taxa Definition:** Establishing analytical frameworks for key species (*Balaena mysticetus*, *Odobenus rosmarus*, *Ursus maritimus*, *Rangifer tarandus*).
3. **Pilot Spatial Analysis:** Co-authoring a pilot analysis on a test sector to showcase the visualization and spatial clustering pipeline.

We look forward to collaborating with you as Co-Principal Investigators on this initiative!
