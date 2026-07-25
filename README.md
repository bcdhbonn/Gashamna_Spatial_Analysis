# Gåshamna Spatial Zooarchaeology & Landscape Analysis

Spatial analysis, density mapping, density-based clustering (DBSCAN), taphonomic disentanglement, and topographic integration for early modern shore-based whaling at **Gåshamna West, Hornsund, Svalbard**.

---

## 📖 Overview & Repository Structure

This repository contains the complete computational workflow implemented in Python for the spatial and zooarchaeological analysis of surface faunal remains (*n* = 628) and 17th–18th century blubber rendering infrastructure at Gåshamna West.

The codebase is organized into **five core Jupyter Notebooks**:

| Notebook | Focus & Methodological Scope | Key Parameters & Output |
| :--- | :--- | :--- |
| **`GAS_Hex_Density.ipynb`** | Standardized 20 m hexagonal density grids across 6 faunal categories | $d = 20.0\text{ m}$, `gridsize=35`, 6-panel A4 Figure 4 |
| **`GAS_DBSCAN.ipynb`** | Density-based activity zone clustering & noise filtering | $eps = 7.0\text{ m}$, $min\_samples = 15$, $k$-distance elbow |
| **`GAS_Anatomic.ipynb`** | Skeletal element representation, Chi-Square & $Z$-score residuals | $\chi^2 = 237.81$, $p = 4.84 \times 10^{-28}$, Cramér's $V = 0.275$ |
| **`GAS_Bone_Size.ipynb`** | Fragmentation metrics & spatial distance-size decay | Spearman $r_s = -0.138$, core vs. peripheral dispersion |
| **`GAS_Topo.ipynb`** | Photogrammetric DEM integration, elevation & slope stability | 0.05 m DEM, $5^\circ$ slope threshold, altitudinal zonation |

---

## 🔬 Notebook Workflows & Analytical Details

### 1. Hexagonal Spatial Density Mapping (`GAS_Hex_Density.ipynb`)
* **Mathematical Grid:** Metric hexagonal tessellation in UTM Zone 33N (EPSG:25833). Cell width $d = 20.0\text{ m}$ (area $A \approx 346.4\text{ m}^2$) matching $2.5$ hexagons along the $50\text{ m}$ scale bar.
* **Taxonomic Layers:** Bowhead whale (*Balaena mysticetus*), Beluga (*Delphinapterus leucas*), Cattle (*Bos taurus*), Polar bear (*Ursus maritimus*), Reindeer (*Rangifer tarandus*), and Arctic fox (*Vulpes lagopus*).
* **Visualization:** High-resolution photogrammetric DEM background (Nordic Tundra colormap), opaque feature overlay (Ovens = Magenta `#e6007e`, Trapper Hut = Cyan `#00bcd4`), North arrow, and $50\text{ m}$ metric scale bar on every panel.

### 2. Density-Based Clustering & Validation (`GAS_DBSCAN.ipynb`)
* **Algorithm:** DBSCAN (*Density-Based Spatial Clustering of Applications with Noise*; Ester et al., 1996).
* **Parameter Validation:**
  * **$k$-Distance Elbow Plot ($k=15$):** Establishes an empirical distance knee-point at $7.0\text{ m}$ separating dense anthropic concentrations from background taphonomic scatter.
  * **Sensitivity Matrix Sweep:** Evaluates 60 parameter combinations ($eps \in [3\text{--}15\text{ m}]$, $min\_samples \in [5\text{--}30]$), demonstrating a broad stability plateau ($n = 8\text{--}11$ clusters) between $eps = 6.0\text{ m}$ and $8.0\text{ m}$.
* **Envelope Generation:** 3.5 m point buffering, unary union dissolve, and Douglas–Peucker simplification ($0.2\text{ m}$ tolerance) producing 9 discrete activity envelopes (Clusters 1–9).

### 3. Anatomical Zoning & Chi-Square Residuals (`GAS_Anatomic.ipynb`)
* **Chi-Square Independence Test:** $\chi^2 = 237.81, df = 45, p = 4.84 \times 10^{-28}$, Cramér's $V = 0.275$.
* **Standardized Pearson Residuals ($Z$-Scores):** $Z = \frac{O - E}{\sqrt{E}}$.
  * **Shoreline Landing Zone (Clusters 1, 3, 4):** Crania & maxillae significantly over-represented ($Z = +2.84$ to $+4.49$), indicating primary beach flensing to extract baleen/cranial oil without hauling heavy skulls uphill.
  * **Interior Oven Zone (Clusters 5 & 6):** Vertebrae significantly over-represented ($Z = +6.03$ to $+7.33$), proving selective transport of axial skeletons inland to blubber rendering ovens.
  * **Peripheral Scatter (Noise -1):** Weathered fragments ($< 20\text{ cm}$) over-represented ($Z = +1.10$ to $+1.46$).

### 4. Fragmentation & Size-Distance Decay (`GAS_Bone_Size.ipynb`)
* **Metric Distribution:** Maximum specimen dimensions range from $< 5\text{ cm}$ fragments to $> 220\text{ cm}$ complete crania.
* **Spatial Decay:** Significant negative Spearman rank correlation ($r_s = -0.138, p < 0.001$) between specimen length and distance to nearest DBSCAN cluster centroid.
* **Interpretation:** Large structural elements ($> 100\text{ cm}$) remain anchored inside core work zones (median distance = $0.0\text{ m}$), whereas small fragments ($< 20\text{ cm}$) are winnowed outward by meltwater runoff, trampling, and frost action.

### 5. Micro-Topography & Slope Gradient Analysis (`GAS_Topo.ipynb`)
* **Terrain Model:** 0.05 m ground resolution UAV-derived photogrammetric DEM adjusted to relative mean sea level baseline.
* **Altitudinal Zonation:** Whale bones span 0.48 to 3.96 m MSL. Low shoreline clusters (1, 3, 9; mean 1.83–2.31 m MSL) mark beach landing sites; elevated terrace clusters (4, 5, 7; mean 2.77–2.96 m MSL) mark secondary processing.
* **Slope Gradient Stability:** Core processing clusters (6, 7, 8, 9) occupy flat marine terraces ($3.61^\circ$ to $4.37^\circ$ mean slope), confirming that primary processing occurred on stable ground where post-depositional slope-wash wash is minimal.

---

## 📚 References

* **Agresti, A. (2007).** *An Introduction to Categorical Data Analysis* (2nd ed.). John Wiley & Sons.
* **Birnie, R. W. (2008).** Hexagonal Binning: A Strategy for Displaying Spatial Density. *Cartography and Geographic Information Science*, 35(2), 123-134.
* **Blankholm, H. P. (1991).** *Intrasite Spatial Analysis in Theory and Practice*. Aarhus University Press.
* **Carr, D. B. et al. (1987).** Scatterplot Matrix Techniques for Large N. *Journal of the American Statistical Association*, 82(398), 424-436.
* **Conolly, J., & Lake, M. (2006).** *Geographical Information Systems in Archaeology*. Cambridge University Press.
* **Crema, E. R. (2022).** Spatial Point Pattern Analysis in Archaeology: Methods, Applications, and Challenges. *Journal of Archaeological Method and Theory*, 29(4), 1120–1148.
* **Drennan, R. D. (2009).** *Statistics for Archaeologists: A Commonsense Approach* (2nd ed.). Springer.
* **Ester, M. et al. (1996).** A Density-Based Algorithm for Discovering Clusters in Large Spatial Databases with Noise. In *KDD-96* (pp. 226-231). AAAI Press.
* **Everitt, B. S. (1992).** *The Analysis of Contingency Tables* (2nd ed.). Chapman & Hall/CRC.
* **Gillings, M. et al. (Eds.). (2020).** *Archaeological Spatial Analysis: A Glossary of Methods*. Routledge.
* **Hacquebord, L. (1984).** *Smeerenburg: Het verblijf van Nederlandse walvisvaarders op Spitsbergen in de zeventiende eeuw*. Mededelingen van het Arctic Centre, 8.
* **Hacquebord, L., & Avango, D. (2016).** Settlements in an Arctic Landscape. *Polar Record*, 52(6), 617-628.
* **Hahsler, M. et al. (2019).** dbscan: Fast Density-Based Clustering with R. *Journal of Statistical Software*, 91(1), 1-30.
* **Lyman, R. L. (1994).** *Vertebrate Taphonomy*. Cambridge University Press.
* **Outram, A. K. (2001).** A New Approach to Identifying Bone Marrow and Grease Exploitation. *International Journal of Osteoarchaeology*, 11(6), 401-410.
* **Schiffer, M. B. (1987).** *Formation Processes of the Archaeological Record*. University of New Mexico Press.
* **Sharpe, D. (2015).** Your Chi-Square Test is Statistically Significant: Now What? *PARE*, 20(8), 1-10.
* **Shennan, S. (1997).** *Quantifying Archaeology* (2nd ed.). Edinburgh University Press.
* **Wheatley, D., & Gillings, M. (2002).** *Spatial Technology and Archaeology*. Taylor & Francis.
* **Zar, J. H. (2010).** *Biostatistical Analysis* (5th ed.). Prentice Hall.