# Arctic Historical Expeditions — Interactive 3D Globe

**Historical Arctic expedition routes reconstructed and visualised on a North Pole–centred interactive globe.**

**By Bartolome Ortiz Viso**  
**License:** [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/) — attribution required.

## About the project

This project presents **36 historical expeditions across the Arctic**, with mapped routes dating from **1553 to 1969**. It brings historical cartography into an interactive environment so that visitors can compare exploration routes over time, examine the geography of the polar regions, and read concise accounts of each expedition.

The globe opens with the **North Pole at its centre**. Each expedition has its own colour, is identified by captain or expedition name and year, and can be explored alone or alongside the other routes. The interactive experience is in English.

## Research and cartographic methodology

1. **Historical map research.** Maps and expedition accounts in books from the **Royal Geographical Society** were consulted as the basis for reconstructing the journeys.
2. **Georeferencing in QGIS.** Historical map sheets were georeferenced against geographic reference points in **QGIS** and their itinerary lines digitised into vector routes.
3. **Geospatial data preparation.** The route geometries were stored as **GeoJSON**, with captain names, starting and ending years, source labels, and short historical descriptions. The geographic coordinates use **CRS84 (longitude–latitude, WGS 84)**.
4. **Interactive visualisation.** A single-page web viewer was created using **HTML5, JavaScript, Canvas and WebGL**. The route data is embedded in the HTML; the viewer renders a North Pole–centred globe, interactive expedition selection, and continuously animated route drawings.

> **Historical accuracy note:** These are cartographic reconstructions from historic maps, not measured GPS tracks. The location and level of detail of each line depend on the original source, its scale, and the georeferencing process. Some historical dates and attributions in the underlying dataset require further validation; they are flagged below rather than silently changed.

## Explore the interactive map

The viewer provides the following functions:

- **North Pole view** to return to the default polar perspective.
- **Show all routes / Hide all routes** to compare the complete dataset or clear the map.
- **Individual route selection** via checkboxes or by choosing an expedition in the list.
- **Fit selected routes** to adjust the view to the selected expeditions.
- **Animated route drawing** with a smoothly overlapping, continuously repeating trace; animation can be turned off.
- **Route identification** using captain/expedition name, year and distinct colours, plus detailed descriptions when a route is selected.
- **Geographic context** including meridians, parallels, country names, polar geographic features, coastlines and boundaries.
- **Search** by expedition name, captain, year or available route text.
- **High-resolution Earth imagery** when online resources are available, with a vector-map fallback.

## Publish with GitHub Pages

1. Save the final viewer as **`index.html`** in the root of your GitHub repository.
2. Place this file alongside it as **`README.md`**.
3. In your repository, open **Settings → Pages** and select **Deploy from a branch**, then **`main`** and **`/ (root)`**.
4. The site will be available at an address similar to `https://YOUR-USERNAME.github.io/YOUR-REPOSITORY/`.

Because the expedition geometries are included within the HTML, **no separate route data file is required** for the website to operate. A network connection is useful for loading the optional satellite texture.

## Dataset and attributes

The dataset contains **36 GeoJSON features**, all represented as `MultiLineString` geometries. The source labels recorded in the file are `RGS`, `RGS UK` and `EGS UK` (reproduced as provided). The dates span from the first recorded start year, **1553**, to the latest recorded end year, **1969**.

| Attribute | Meaning |
|---|---|
| `id`, `fid` | Original record identifiers |
| `capitan` | Captain or expedition name, as entered in the source dataset |
| `inicio` | Recorded starting year |
| `fin` | Recorded ending year |
| `desc` | Expanded historical description (2–3 sentences) |
| `desc_original` | Original short note, preserved where available |
| `fuente` | Original source label recorded for the mapped route |
| `desc_source_url` | Contextual historical reference used for the description |
| `desc_review_note` | Warning where an attribution or year should be reviewed |

The exact titles, editions, page numbers and map plates of the Royal Geographical Society volumes are not listed in the GeoJSON; they should be added to the bibliography if known. The links provided with the descriptions below are **contextual references**, not necessarily citations to the precise map plate used for georeferencing.

## Catalogue of all 36 historical expeditions

The expedition names and date values below follow the original dataset, including spelling and dating anomalies. Descriptions are taken from the expanded `desc` attribute; historical reference links are drawn from `desc_source_url`.

### 16th century


**01. Chancellor — 1553–1554**

Richard Chancellor sailed with the 1553 English expedition seeking a northeastern sea route to Asia and reached the White Sea after becoming separated from Hugh Willoughby's ships. He traveled inland along the Northern Dvina route to Moscow, where his contacts with Ivan IV helped establish commercial relations between England and Russia.

Original map source label: `RGS UK` · [Historical reference](https://www.encyclopedia.com/people/history/explorers-travelers-and-conquerors-biographies/richard-chancellor).

**02. Willoughby — 1553–1555**

Hugh Willoughby led the 1553 English search for a northeastern passage to Asia, accompanied initially by Richard Chancellor. Storms separated their ships, and Willoughby's vessels were forced to winter on the Russian Arctic coast; Willoughby and his crews died before they could return.

Original map source label: `RGS` · [Historical reference](https://www.encyclopedia.com/people/history/explorers-travelers-and-conquerors-biographies/richard-chancellor).

**03. Borough — 1556**

Stephen Borough sailed the small vessel Searchthrift in 1556 to investigate a possible northeastern passage beyond the White Sea. He explored toward Vaigach Island and the Kara Strait, adding valuable navigational knowledge even though ice and weather prevented a passage to Asia.

Original map source label: `RGS` · [Historical reference](https://www.gutenberg.net.au/ebooks13/1305581h.html).

**04. Frobisher — 1576 *(recorded end year: 11576; see data note)***

Martin Frobisher left England in 1576 searching for a Northwest Passage to Asia and crossed the North Atlantic toward the Canadian Arctic. He explored the inlet later named Frobisher Bay, initially mistaking it for a promising route westward; the voyage helped launch further expeditions to the same region.

Original map source label: `RGS` · [Historical reference](https://www.rmg.co.uk/stories/maritime-history/martin-frobisher-north-west-passage-expedition-1576-78).

> **Data review note:** Original end-year value '11576' appears to be a typing error for '1576'; not changed.

**05. Frobisher — 1578**

Frobisher's third voyage in 1578 returned to the Canadian Arctic with a large fleet whose primary aim was to collect ore thought to contain gold. Ice and difficult conditions disrupted the venture, and the ore subsequently proved to be of no commercial value, ending this particular Arctic mining scheme.

Original map source label: `RGS` · [Historical reference](https://www.rmg.co.uk/stories/maritime-history/martin-frobisher-north-west-passage-expedition-1576-78).

**06. Davis — 1585 *(recorded end year: 11585; see data note)***

John Davis led his first Northwest Passage expedition in 1585, sailing from England toward Greenland and the waters west of it. His exploration opened a sustained investigation of the strait that now bears his name and improved English knowledge of Arctic approaches to North America.

Original map source label: `RGS` · [Historical reference](https://www.rmg.co.uk/stories/maritime-history/john-davis-north-west-passage-expeditions-1585-87).

> **Data review note:** Original end-year value '11585' appears to be a typing error for '1585'; not changed.

**07. Davis — 1587**

On his third Arctic voyage in 1587, John Davis pushed farther north through Davis Strait along Greenland's western side before ice prevented further progress. His observations and charting contributed substantially to European knowledge of the waters between Greenland and Baffin Island.

Original map source label: `RGS` · [Historical reference](https://www.rmg.co.uk/stories/maritime-history/john-davis-north-west-passage-expeditions-1585-87).

### 17th century


**08. Baffin — 1610–1611**

This route is attributed in the original dataset to William Baffin in 1610–1611, but reliable biographical records place his first documented Arctic voyage in 1612. Baffin later explored Northwest Passage approaches with Robert Bylot, notably in 1615–1616, so the captain and date assigned to this route require verification.

Original map source label: `RGS` · [Historical reference](https://www.biographi.ca/en/bio/baffin_william_1E.html).

> **Data review note:** The 1610–1611 attribution to William Baffin is inconsistent with the documented chronology of his voyages; needs checking against the original map.

**09. Hudson — 1610–1611**

Henry Hudson sailed in the Discovery in 1610 to search for a Northwest Passage and entered the great inland sea later named Hudson Bay. The expedition wintered in James Bay, but in 1611 a mutiny left Hudson and several companions adrift, and they were never seen again.

Original map source label: `RGS` · [Historical reference](https://www.rmg.co.uk/stories/maritime-history/henry-hudson-north-west-passage-expedition-1610-11).

### 18th century


**10. Middelton — 1742**

Christopher Middleton's 1742 expedition explored northern Hudson Bay while searching for a navigable route westward toward the Pacific. He surveyed the areas of Wager Bay and Repulse Bay, gathering geographic evidence but finding no Northwest Passage through those waters.

Original map source label: `RGS` · [Historical reference](https://en.wikisource.org/wiki/Page:Encyclop%C3%A6dia_Britannica%2C_Ninth_Edition%2C_v._10.djvu/204).

**11. Hearne — 1771–1772**

Samuel Hearne travelled from Fort Prince of Wales with the Dene leader Matonabbee and Indigenous companions, reaching the Coppermine River and Arctic coast in July 1771. They returned to Hudson Bay in June 1772, and the journey contributed important observations about northern Canada's geography, although some recorded positions were inaccurate.

Original map source label: `RGS` · [Historical reference](https://www.biographi.ca/en/bio/hearne_samuel_4E.html).

**12. Phipps — 1773**

Constantine John Phipps commanded HMS Racehorse on a 1773 voyage that attempted to push north toward the Pole from the waters around Svalbard. Together with HMS Carcass, the expedition reached approximately 80°50′ N before pack ice blocked further progress, while its crew made scientific and navigational observations.

Original map source label: `RGS UK` · [Historical reference](https://www.npg.org.uk/collections/search/portraitExtended/mw04564/Constantine-John-Phipps-2nd-Baron-Mulgrave).

**13. Mackenzie — 1789**

In 1789 Alexander Mackenzie, travelling with Indigenous companions including Dene guide Aw-gee-nah, followed the river now bearing Mackenzie's name from Great Slave Lake to the Arctic Ocean. The journey established that the great northwest-flowing river did not lead to the Pacific, a result of major geographical importance.

Original map source label: `RGS` · [Historical reference](https://www.canada.ca/en/parks-canada/news/2016/02/sir-alexander-mackenzie-c-1762-1820-.html).

### 19th century


**14. Buchan and Franklin — 1818**

Captain David Buchan led an 1818 British voyage north of Svalbard in HMS Dorothea, accompanied by HMS Trent under the command of John Franklin. The vessels attempted to reach high latitudes in search of a route toward the North Pole, but heavy sea ice and damage forced them to turn back.

Original map source label: `RGS` · [Historical reference](https://www.biographi.ca/en/bio/franklin_john_7F.html).

**15. Jown Ross and Parry — 1818**

John Ross commanded the 1818 British search for the Northwest Passage through Davis Strait and Baffin Bay, with William Edward Parry commanding HMS Alexander alongside Ross's HMS Isabella. Ross turned back after believing that Lancaster Sound was blocked by land, a decision later challenged when Parry explored the route further.

Original map source label: `RGS` · [Historical reference](https://www.biographi.ca/en/bio/4170?revision_id=3005).

**16. Franklin — 1819–1822**

John Franklin's first overland Arctic expedition, from 1819 to 1822, travelled through the Canadian interior and down the Coppermine River to the Arctic coast. The party surveyed coastal waters to the east, but extreme shortages and a disastrous return march caused several deaths before the survivors reached safety.

Original map source label: `RGS` · [Historical reference](https://www.biographi.ca/en/bio/franklin_john_7E.html).

**17. Paary — 1819–1820**

William Edward Parry led the 1819–1820 voyage of HMS Hecla and HMS Griper westward through Lancaster Sound in another attempt to find the Northwest Passage. The expedition reached the region of Melville Island and overwintered in the Arctic, making significant advances in navigation and charting before returning to Britain.

Original map source label: `RGS` · [Historical reference](https://static-prod.lib.princeton.edu/visual_materials/maps/websites/northwest-passage/parry-first.htm).

**18. Parry — 1821–1823**

During his 1821–1823 expedition aboard HMS Fury and HMS Hecla, William Edward Parry sought a Northwest Passage through Hudson Strait and Foxe Basin. The crew explored Fury and Hecla Strait and spent winters near Winter Island and Igloolik, but persistent sea ice prevented a full passage westward.

Original map source label: `RGS` · [Historical reference](https://www.biographi.ca/en/bio/parry_william_edward_8E.html).

**19. Franklin — 1825–1827**

John Franklin's second overland Arctic expedition, conducted from 1825 to 1827, descended the Mackenzie River and surveyed the northern mainland coast of North America. Franklin explored westward toward Alaska while John Richardson's party charted coastlines to the east, greatly extending European maps of the region.

Original map source label: `RGS` · [Historical reference](https://www.biographi.ca/en/bio/franklin_john_7F.html).

**20. Ross — 1829–1833**

John Ross's expedition aboard the Victory explored Prince Regent Inlet and Boothia Peninsula between 1829 and 1833, enduring four winters in the Arctic. His nephew James Clark Ross located the North Magnetic Pole in 1831, and the expedition eventually escaped after abandoning its icebound vessel.

Original map source label: `RGS` · [Historical reference](https://www.biographi.ca/en/bio/4170).

**21. Back — 1833–1834**

George Back's overland expedition of 1833–1835 originally set out to seek the missing explorer John Ross and then continued to survey the Great Fish River, now the Back River, toward the Arctic coast. The journey helped map a difficult route through northern Canada and was undertaken with substantial Indigenous and Hudson's Bay Company assistance.

Original map source label: `RGS` · [Historical reference](https://www.biographi.ca/en/bio/back_george_10E.html).

> **Data review note:** The dataset ends this route in 1834, while Back's broader expedition continued into 1835; original dates retained.

**22. Dease and Simpson — 1837–1839**

Peter Warren Dease and Thomas Simpson led Hudson's Bay Company surveys of the Canadian Arctic coastline between 1837 and 1839. Their expeditions traced previously unmapped sections toward Point Barrow in Alaska and east toward King William Island, narrowing gaps in knowledge of the Northwest Passage.

Original map source label: `RGS` · [Historical reference](https://ice.lindahall.org/20_dease.shtml).

**23. Franklin — 1845–1847**

John Franklin departed in 1845 with HMS Erebus and HMS Terror to seek the Northwest Passage through the Canadian Arctic. Both ships became trapped near King William Island in 1846; Franklin died in 1847 and the surviving crews abandoned the vessels in 1848, setting off decades of search expeditions.

Original map source label: `RGS` · [Historical reference](https://parks.canada.ca/lhn-nhs/nu/epaveswrecks/culture/histoire-history/expedition).

> **Data review note:** The dataset ends this expedition in 1847 (Franklin's death), while his surviving crew abandoned its ships in 1848; original dates retained.

**24. MCluer — 1850–1854**

Robert McClure sailed HMS Investigator into the Arctic from the Pacific in 1850 while searching for Franklin and a Northwest Passage. His ship became trapped near Banks Island, and the crew ultimately travelled by sledge to rescue vessels coming from the east, completing the first documented traversal of the passage using both ship and overland travel.

Original map source label: `RGS` · [Historical reference](https://umanitoba.ca/libraries/archives-special-collections/arctic-blue-books/1854a).

**25. MClintock — 1857–1859**

Francis Leopold McClintock commanded the yacht Fox between 1857 and 1859 in a privately supported search for the lost Franklin expedition. His party recovered crucial written evidence on King William Island documenting Franklin's death and the later abandonment of HMS Erebus and HMS Terror.

Original map source label: `RGS` · [Historical reference](https://parks.canada.ca/lhn-nhs/nu/epaveswrecks/culture/histoire-history/qui-who.).

**26. Nares — 1875–1876**

George Nares led the British Arctic Expedition of 1875–1876 into Smith Sound aboard HMS Alert and HMS Discovery, exploring the region north of Ellesmere Island. His teams undertook demanding sledge journeys, including a record-setting push by Albert Markham's party, but ice and illness prevented the hoped-for advance to the Pole.

Original map source label: `RGS` · [Historical reference](https://www.polarpostalhistory.org.uk/polar-galleries-expeditions/index).

**27. Nansen — 1888**

Fridtjof Nansen and five companions made the first successful crossing of Greenland's inland ice from east to west in 1888, travelling on skis and sledges. After reaching the western coast, they spent the winter of 1888–1889 in Greenland before returning to Norway.

Original map source label: `RGS` · [Historical reference](https://frammuseum.no/en/polar-history/expeditions/polar-history-expeditions-across-the-greenland-ice-1888-1889/).

**28. Nansen — 1893–1896**

Fridtjof Nansen's Fram expedition began in 1893 with the deliberate freezing of the vessel into pack ice near Siberia so that ocean currents could carry it across the Arctic. The ship drifted for years while observations of sea depth, ice and currents advanced polar science; its crew returned safely in 1896.

Original map source label: `RGS` · [Historical reference](https://frammuseum.no/en/polar-history/expeditions/the-first-fram-expedition-1893-1896/).

**29. Nansen — 1894**

This mapped line appears to represent Nansen's sledge journey from the icebound Fram toward the North Pole during the 1893–1896 expedition. Nansen and Hjalmar Johansen actually began that journey in March 1895, reaching a then-record northern latitude before retreating toward Franz Josef Land; the 1894 label in this GeoJSON therefore needs verification.

Original map source label: `RGS` · [Historical reference](https://frammuseum.no/en/polar-history/expeditions/the-first-fram-expedition-1893-1896/).

> **Data review note:** The GeoJSON assigns 1894, but Nansen's well-documented sledge departure from Fram was in March 1895.

### 20th century


**30. Amundsen — 1903–1906**

Roald Amundsen sailed the small vessel Gjøa through the Canadian Arctic from 1903 to 1906, completing the first successful Northwest Passage voyage by a single ship. The crew overwintered near King William Island and gathered magnetic and geographic observations before reaching Alaska.

Original map source label: `RGS` · [Historical reference](https://www.rmg.co.uk/stories/maritime-history/roald-amundsen-north-west-passage-expedition-1903-06).

**31. Peary — 1909**

Robert Peary's 1909 expedition travelled north from Ellesmere Island by dog sledge across the Arctic sea ice, supported by a party that included Matthew Henson and Inuit explorers. Peary claimed to have reached the North Pole on 6 April 1909, but historians continue to debate whether the party actually attained the precise geographical pole.

Original map source label: `RGS` · [Historical reference](https://www.smithsonianmag.com/history/who-discovered-the-north-pole-116633746/).

**32. Stefansson — 1913–1918**

Vilhjalmur Stefansson led the northern party of the Canadian Arctic Expedition of 1913–1918, exploring Beaufort Sea waters and islands of the western Canadian Arctic. The expedition combined coastal surveys, scientific observations and extensive travel across sea ice, although it was also marked by serious hardships and losses.

Original map source label: `RGS` · [Historical reference](https://www2.whoi.edu/site/beaufortgyre/history/the-canadian-arctic-expedition-1913-1918/).

**33. Nobile — 1926**

Umberto Nobile commanded the airship Norge on the celebrated 1926 transpolar flight organized with Roald Amundsen and Lincoln Ellsworth. The aircraft passed over the North Pole after departing Svalbard and continued across the Arctic Ocean to Alaska, demonstrating the possibilities of long-range polar aviation.

Original map source label: `RGS` · [Historical reference](https://svalbardmuseum.no/en/amundsens-and-nobiles-airship-voyages).

**34. Nobile — 1928**

During the 1928 Italia expedition, Umberto Nobile made exploratory airship flights from the base at Ny-Ålesund on Svalbard. One major eastward flight passed the Franz Josef Land region toward Severnaya Zemlya before returning, extending aerial observations of the high Arctic.

Original map source label: `EGS UK` · [Historical reference](https://link.springer.com/article/10.1007/s00016-025-00338-9).

**35. Nobile — 1928**

In May 1928 Umberto Nobile flew the airship Italia from Svalbard to the North Pole and attempted to return to base. The airship crashed onto drifting pack ice northeast of Svalbard, triggering a major international rescue operation that saved several survivors but also resulted in further losses.

Original map source label: `RGS` · [Historical reference](https://svalbardmuseum.no/en/amundsens-and-nobiles-airship-voyages).

**36. Herbert — 1968–1969**

Wally Herbert led the British Trans-Arctic Expedition of 1968–1969 across the frozen Arctic Ocean by dog sledge, travelling from Alaska toward Svalbard. The four-man team passed through the North Pole in April 1969 and completed a pioneering surface crossing of the Arctic Ocean in May.

Original map source label: `RGS` · [Historical reference](https://www.guinnessworldrecords.com/world-records/67801-first-crossing-of-the-arctic).

## Source-critical notes

The expanded GeoJSON contains review notes for six records. Particular caution is needed with these entries:

- **Frobisher (1576)** and **Davis (1585):** the original end-year values are `11576` and `11585` respectively; both appear to be transcription errors.
- **Baffin (1610–1611):** the assigned date conflicts with the documented chronology of William Baffin’s voyages.
- **Back (1833–1834):** the mapped date range ends in 1834, although the broader expedition extended into 1835.
- **Franklin (1845–1847):** the dataset ends in 1847 (the year of Franklin’s death); the surviving crews abandoned the ships in 1848.
- **Nansen (1894):** the sledge journey described here began in 1895, so the map’s 1894 attribution should be checked.

These are comments on **metadata**, not modifications to the mapped coordinates. In keeping with the historical source record, the original date and name fields have been preserved.

## Credits and licence

**Project, cartographic reconstruction, expanded historical captions and interactive viewer:** Bartolome Ortiz Viso.

The author releases the original material for which they hold rights under **[Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/)**. You may share and adapt that material, including for commercial purposes, **provided that you give appropriate credit, link to the licence and indicate if changes were made**.

**Suggested attribution:**

> Arctic Historical Expeditions — Interactive 3D Globe, by Bartolome Ortiz Viso, licensed under CC BY 4.0. [Link to the published project]. Changes, if any, should be indicated.

**Third-party material:** The optional high-resolution Earth texture is credited to **Solar System Scope** and is published on Wikimedia Commons under **CC BY 4.0**: [Earth daymap, 8K](https://commons.wikimedia.org/wiki/File:Solarsystemscope_texture_8k_earth_daymap.jpg). Other historic maps and source works may have separate rights or reuse conditions; the author’s CC BY notice does not override those rights.

**Additional mapping context:** Country and geographical labels and the geographical reference material used in the reconstruction are provided for educational and visual exploration; consult original map sources for research-grade attribution.

## Further work

Potential extensions include detailed Royal Geographical Society map bibliographic records, documented georeferencing control points and accuracy, a chronological timeline, original map scans linked to each route, and multilingual captions.

---

**Author:** Bartolome Ortiz Viso · **License:** [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)
