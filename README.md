# Arctic Historical Expeditions — Interactive 3D Globe

**By Bartolome Ortiz Viso** · **36 Arctic expeditions (1553–1969)**

**License for original contributions:** [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/) — attribution required.

## About the project

This interactive map presents **36 historical Arctic expedition routes** dating from **1553 to 1969**, reconstructed from historical cartographic sources. The globe starts with the North Pole at its centre and allows visitors to examine individual voyages or compare the routes together. Every expedition has its own colour, name, year and short historical description.

The purpose is to make the geography and chronology of Arctic exploration easier to examine in a single interactive visualisation. These tracks are **reconstructions of historical charts, not recorded GPS positions**.

## Methodology

1. **Historical sources:** consultation of books, historical maps and expedition accounts associated with the **Royal Geographical Society**. The short historical descriptions have also been checked against published museum, government and biographical references linked for each entry below.
2. **Georeferencing:** historical maps were georeferenced in **QGIS**, using identifiable geographic reference points; the expedition tracks were digitised as vector linework.
3. **Data:** the digitised routes are stored in `rutas_artico.geojson`, using **CRS84 (WGS 84 longitude–latitude)** and the original feature geometry. Each record includes the captain (`capitan`), start year (`inicio`), end year (`fin`), source (`fuente`) and description (`desc`).
4. **Visualisation:** the viewer uses **HTML5, JavaScript, Canvas and WebGL** to render a North Pole–centred interactive globe. Route geometries are embedded in `index.html`, with continuous overlapping drawing animations. A satellite basemap is loaded when available; a vector fallback remains available if it cannot be retrieved.

**Source limitation:** the exact bibliographic editions, pages and plates of the Royal Geographical Society maps are not recorded in the original dataset. The historical-reference links below support contextual dating and descriptions but should not be mistaken for direct citations to the specific georeferenced map plates. Some line geometry remains approximate because it was digitised from historical maps.

## Using the interactive globe

- **Show all routes** and **Hide all routes** to display or clear all 36 voyages.
- **Select expeditions** using checkboxes or click a name to focus on a single route.
- **North Pole view** and **Fit selected routes** to reset or focus the viewpoint.
- **Seamless animated route drawing**, with each new drawing beginning before the previous one finishes; disable it using the layer toggle.
- **Labels and descriptions** with captain, year and expedition context.
- **Map layers:** meridians and parallels, country names, geographic place names, coastlines and boundaries.
- **Search** by name, dates and available notes.

## Files and GitHub Pages

| File | Purpose |
|---|---|
| `index.html` | Self-contained expedition viewer, including all 36 route geometries and descriptions. |
| `rutas_artico.geojson` | Editable geospatial dataset with verified dates, original-date fields and correction notes. |
| `README.md` | Project methodology, sources, historical catalogue and license. |

To publish, upload all three files to the root of a public GitHub repository. In **Settings → Pages**, choose **Deploy from a branch → main → / (root)**. GitHub Pages will serve `index.html` as the homepage. The website does **not** require a separate request to the GeoJSON file, as its route data is already embedded in the HTML. An internet connection is needed for externally hosted imagery to load.

## Dataset fields

| Attribute | Meaning |
|---|---|
| `fid`, `id` | Original record identifiers; note that `id` is not unique in the source. |
| `capitan` | Captain / expedition label from the original digitisation. |
| `inicio`, `fin` | Reviewed year range used by the website and catalogue. |
| `inicio_original`, `fin_original` | Unaltered source year values. |
| `date_correction_note` | Explanation of a corrected date (on revised records). |
| `date_reference_url` | External historical reference supporting the correction. |
| `desc` | Historical description (2–3 sentences). |
| `desc_original` | Original short source note, if any. |
| `desc_source_url` | Contextual historical source for the description. |
| `desc_review_note` | Remaining uncertainty, where applicable. |
| `fuente` | Original map-source label (`RGS`, `RGS UK`, `EGS UK`). |

## Catalogue of 36 Arctic expeditions

All names, dates, descriptions and links in this catalogue are generated from the corrected GeoJSON. The ordering follows the revised start year, then the name and original feature index. The corrected labels are also used by the interactive viewer.

### 01. Chancellor — 1553–1554

Richard Chancellor sailed with the 1553 English expedition seeking a northeastern sea route to Asia and reached the White Sea after becoming separated from Hugh Willoughby's ships. He traveled inland along the Northern Dvina route to Moscow, where his contacts with Ivan IV helped establish commercial relations between England and Russia.

Source label: `RGS UK` · [Historical reference](https://www.encyclopedia.com/people/history/explorers-travelers-and-conquerors-biographies/richard-chancellor).

### 02. Willoughby — 1553–1554

Hugh Willoughby led an English expedition in 1553 to seek a Northeast Passage to Asia, initially sailing alongside Richard Chancellor. After storms separated their vessels, Willoughby's ships wintered on the Kola Peninsula, where he and his crews died in early 1554.

Source label: `RGS` · [Historical reference](https://www.encyclopedia.com/history/encyclopedias-almanacs-transcripts-and-maps/willoughby-sir-hugh).

*Date review: 1554 is the year of Willoughby’s death during wintering following the 1553 voyage, not 1555. [Reference](https://www.encyclopedia.com/history/encyclopedias-almanacs-transcripts-and-maps/willoughby-sir-hugh).*

### 03. Borough — 1556

Stephen Borough sailed the small vessel Searchthrift in 1556 to investigate a possible northeastern passage beyond the White Sea. He explored toward Vaigach Island and the Kara Strait, adding valuable navigational knowledge even though ice and weather prevented a passage to Asia.

Source label: `RGS` · [Historical reference](https://www.gutenberg.net.au/ebooks13/1305581h.html).

### 04. Frobisher — 1576

Martin Frobisher left England in 1576 searching for a Northwest Passage to Asia and crossed the North Atlantic toward the Canadian Arctic. He explored the inlet later named Frobisher Bay, initially mistaking it for a promising route westward; the voyage helped launch further expeditions to the same region.

Source label: `RGS` · [Historical reference](https://www.rmg.co.uk/stories/maritime-history/martin-frobisher-north-west-passage-expedition-1576-78).

*Date review: Corrected a five-digit transcription error (11576) to 1576 for Frobisher’s first voyage. [Reference](https://www.rmg.co.uk/stories/maritime-history/martin-frobisher-north-west-passage-expedition-1576-78).*

### 05. Frobisher — 1578

Frobisher's third voyage in 1578 returned to the Canadian Arctic with a large fleet whose primary aim was to collect ore thought to contain gold. Ice and difficult conditions disrupted the venture, and the ore subsequently proved to be of no commercial value, ending this particular Arctic mining scheme.

Source label: `RGS` · [Historical reference](https://www.rmg.co.uk/stories/maritime-history/martin-frobisher-north-west-passage-expedition-1576-78).

### 06. Davis — 1585

John Davis led his first Northwest Passage expedition in 1585, sailing from England toward Greenland and the waters west of it. His exploration opened a sustained investigation of the strait that now bears his name and improved English knowledge of Arctic approaches to North America.

Source label: `RGS` · [Historical reference](https://www.rmg.co.uk/stories/maritime-history/john-davis-north-west-passage-expeditions-1585-87).

*Date review: Corrected a five-digit transcription error (11585) to 1585 for Davis’s first Northwest Passage voyage. [Reference](https://www.rmg.co.uk/stories/maritime-history/john-davis-north-west-passage-expeditions-1585-87).*

### 07. Davis — 1587

On his third Arctic voyage in 1587, John Davis pushed farther north through Davis Strait along Greenland's western side before ice prevented further progress. His observations and charting contributed substantially to European knowledge of the waters between Greenland and Baffin Island.

Source label: `RGS` · [Historical reference](https://www.rmg.co.uk/stories/maritime-history/john-davis-north-west-passage-expeditions-1585-87).

### 08. Hudson — 1610–1611

Henry Hudson sailed in the Discovery in 1610 to search for a Northwest Passage and entered the great inland sea later named Hudson Bay. The expedition wintered in James Bay, but in 1611 a mutiny left Hudson and several companions adrift, and they were never seen again.

Source label: `RGS` · [Historical reference](https://www.rmg.co.uk/stories/maritime-history/henry-hudson-north-west-passage-expedition-1610-11).

### 09. Baffin — 1616

William Baffin served as navigator under Robert Bylot on a 1616 voyage through Davis Strait into the bay that now bears Baffin's name. Their vessel explored the approaches to Smith Sound, Jones Sound and Lancaster Sound before returning to England. This mapped route matches the 1616 geographic itinerary more closely than its former 1610–1611 dates, although the original historical map should still be checked to confirm the identification.

Source label: `RGS` · [Historical reference](https://www.rmg.co.uk/stories/maritime-history/william-baffin-robert-bylot-north-west-passage-expedition-1615-16).

*Date review: The Arctic Baffin Bay circuit mapped here is consistent with Baffin and Bylot’s second voyage in 1616, not 1610–1611 (Hudson’s voyage). Attribution to this specific map route remains provisional pending verification against its original plate. [Reference](https://www.rmg.co.uk/stories/maritime-history/william-baffin-robert-bylot-north-west-passage-expedition-1615-16).*

### 10. Middelton — 1742

Christopher Middleton's 1742 expedition explored northern Hudson Bay while searching for a navigable route westward toward the Pacific. He surveyed the areas of Wager Bay and Repulse Bay, gathering geographic evidence but finding no Northwest Passage through those waters.

Source label: `RGS` · [Historical reference](https://en.wikisource.org/wiki/Page:Encyclop%C3%A6dia_Britannica%2C_Ninth_Edition%2C_v._10.djvu/204).

### 11. Hearne — 1771–1772

Samuel Hearne travelled from Fort Prince of Wales with the Dene leader Matonabbee and Indigenous companions, reaching the Coppermine River and Arctic coast in July 1771. They returned to Hudson Bay in June 1772, and the journey contributed important observations about northern Canada's geography, although some recorded positions were inaccurate.

Source label: `RGS` · [Historical reference](https://www.biographi.ca/en/bio/hearne_samuel_4E.html).

### 12. Phipps — 1773

Constantine John Phipps commanded HMS Racehorse on a 1773 voyage that attempted to push north toward the Pole from the waters around Svalbard. Together with HMS Carcass, the expedition reached approximately 80°50′ N before pack ice blocked further progress, while its crew made scientific and navigational observations.

Source label: `RGS UK` · [Historical reference](https://www.npg.org.uk/collections/search/portraitExtended/mw04564/Constantine-John-Phipps-2nd-Baron-Mulgrave).

### 13. Mackenzie — 1789

In 1789 Alexander Mackenzie, travelling with Indigenous companions including Dene guide Aw-gee-nah, followed the river now bearing Mackenzie's name from Great Slave Lake to the Arctic Ocean. The journey established that the great northwest-flowing river did not lead to the Pacific, a result of major geographical importance.

Source label: `RGS` · [Historical reference](https://www.canada.ca/en/parks-canada/news/2016/02/sir-alexander-mackenzie-c-1762-1820-.html).

### 14. Buchan and Franklin — 1818

Captain David Buchan led an 1818 British voyage north of Svalbard in HMS Dorothea, accompanied by HMS Trent under the command of John Franklin. The vessels attempted to reach high latitudes in search of a route toward the North Pole, but heavy sea ice and damage forced them to turn back.

Source label: `RGS` · [Historical reference](https://www.biographi.ca/en/bio/franklin_john_7F.html).

### 15. Jown Ross and Parry — 1818

John Ross commanded the 1818 British search for the Northwest Passage through Davis Strait and Baffin Bay, with William Edward Parry commanding HMS Alexander alongside Ross's HMS Isabella. Ross turned back after believing that Lancaster Sound was blocked by land, a decision later challenged when Parry explored the route further.

Source label: `RGS` · [Historical reference](https://www.biographi.ca/en/bio/4170?revision_id=3005).

### 16. Franklin — 1819–1822

John Franklin's first overland Arctic expedition, from 1819 to 1822, travelled through the Canadian interior and down the Coppermine River to the Arctic coast. The party surveyed coastal waters to the east, but extreme shortages and a disastrous return march caused several deaths before the survivors reached safety.

Source label: `RGS` · [Historical reference](https://www.biographi.ca/en/bio/franklin_john_7E.html).

### 17. Paary — 1819–1820

William Edward Parry led the 1819–1820 voyage of HMS Hecla and HMS Griper westward through Lancaster Sound in another attempt to find the Northwest Passage. The expedition reached the region of Melville Island and overwintered in the Arctic, making significant advances in navigation and charting before returning to Britain.

Source label: `RGS` · [Historical reference](https://static-prod.lib.princeton.edu/visual_materials/maps/websites/northwest-passage/parry-first.htm).

### 18. Parry — 1821–1823

During his 1821–1823 expedition aboard HMS Fury and HMS Hecla, William Edward Parry sought a Northwest Passage through Hudson Strait and Foxe Basin. The crew explored Fury and Hecla Strait and spent winters near Winter Island and Igloolik, but persistent sea ice prevented a full passage westward.

Source label: `RGS` · [Historical reference](https://www.biographi.ca/en/bio/parry_william_edward_8E.html).

### 19. Franklin — 1825–1827

John Franklin's second overland Arctic expedition, conducted from 1825 to 1827, descended the Mackenzie River and surveyed the northern mainland coast of North America. Franklin explored westward toward Alaska while John Richardson's party charted coastlines to the east, greatly extending European maps of the region.

Source label: `RGS` · [Historical reference](https://www.biographi.ca/en/bio/franklin_john_7F.html).

### 20. Ross — 1829–1833

John Ross's expedition aboard the Victory explored Prince Regent Inlet and Boothia Peninsula between 1829 and 1833, enduring four winters in the Arctic. His nephew James Clark Ross located the North Magnetic Pole in 1831, and the expedition eventually escaped after abandoning its icebound vessel.

Source label: `RGS` · [Historical reference](https://www.biographi.ca/en/bio/4170).

### 21. Back — 1833–1835

George Back's overland expedition of 1833–1835 originally set out to seek the missing explorer John Ross and then continued to survey the Great Fish River, now the Back River, toward the Arctic coast. The journey helped map a difficult route through northern Canada and was undertaken with substantial Indigenous and Hudson's Bay Company assistance.

Source label: `RGS` · [Historical reference](https://www.biographi.ca/en/bio/back_george_10E.html).

*Date review: Back’s Arctic land expedition lasted from 1833 to 1835; the mapped coastal survey took place mainly in 1834. [Reference](https://www.biographi.ca/en/bio/back_george_10E.html).*

### 22. Dease and Simpson — 1837–1839

Peter Warren Dease and Thomas Simpson led Hudson's Bay Company surveys of the Canadian Arctic coastline between 1837 and 1839. Their expeditions traced previously unmapped sections toward Point Barrow in Alaska and east toward King William Island, narrowing gaps in knowledge of the Northwest Passage.

Source label: `RGS` · [Historical reference](https://ice.lindahall.org/20_dease.shtml).

### 23. Franklin — 1845–1848

John Franklin departed in 1845 with HMS Erebus and HMS Terror to seek the Northwest Passage through the Canadian Arctic. Both ships became trapped near King William Island in 1846; Franklin died in 1847 and the surviving crews abandoned the vessels in 1848, setting off decades of search expeditions.

Source label: `RGS` · [Historical reference](https://parks.canada.ca/lhn-nhs/nu/epaveswrecks/culture/histoire-history/expedition).

*Date review: Franklin died in 1847, but his surviving expedition continued and the ships were abandoned in April 1848. The 1848 endpoint refers to the last major documentary event, not a successful return. [Reference](https://parks.canada.ca/lhn-nhs/nu/epaveswrecks/culture/histoire-history/expedition).*

### 24. MCluer — 1850–1854

Robert McClure sailed HMS Investigator into the Arctic from the Pacific in 1850 while searching for Franklin and a Northwest Passage. His ship became trapped near Banks Island, and the crew ultimately travelled by sledge to rescue vessels coming from the east, completing the first documented traversal of the passage using both ship and overland travel.

Source label: `RGS` · [Historical reference](https://umanitoba.ca/libraries/archives-special-collections/arctic-blue-books/1854a).

### 25. MClintock — 1857–1859

Francis Leopold McClintock commanded the yacht Fox between 1857 and 1859 in a privately supported search for the lost Franklin expedition. His party recovered crucial written evidence on King William Island documenting Franklin's death and the later abandonment of HMS Erebus and HMS Terror.

Source label: `RGS` · [Historical reference](https://parks.canada.ca/lhn-nhs/nu/epaveswrecks/culture/histoire-history/qui-who.).

### 26. Nares — 1875–1876

George Nares led the British Arctic Expedition of 1875–1876 into Smith Sound aboard HMS Alert and HMS Discovery, exploring the region north of Ellesmere Island. His teams undertook demanding sledge journeys, including a record-setting push by Albert Markham's party, but ice and illness prevented the hoped-for advance to the Pole.

Source label: `RGS` · [Historical reference](https://www.polarpostalhistory.org.uk/polar-galleries-expeditions/index).

### 27. Nansen — 1888

Fridtjof Nansen and five companions made the first successful crossing of Greenland's inland ice from east to west in 1888, travelling on skis and sledges. After reaching the western coast, they spent the winter of 1888–1889 in Greenland before returning to Norway.

Source label: `RGS` · [Historical reference](https://frammuseum.no/en/polar-history/expeditions/polar-history-expeditions-across-the-greenland-ice-1888-1889/).

### 28. Nansen — 1893–1896

Fridtjof Nansen's Fram expedition began in 1893 with the deliberate freezing of the vessel into pack ice near Siberia so that ocean currents could carry it across the Arctic. The ship drifted for years while observations of sea depth, ice and currents advanced polar science; its crew returned safely in 1896.

Source label: `RGS` · [Historical reference](https://frammuseum.no/en/polar-history/expeditions/the-first-fram-expedition-1893-1896/).

### 29. Nansen — 1895

Fridtjof Nansen and Hjalmar Johansen set out from the icebound Fram in March 1895 on a dog-sledge attempt to reach the North Pole. After reaching 86°14′ N, they turned toward Franz Josef Land and arrived there later in 1895. This route depicts that 1895 sledge phase; they wintered in Franz Josef Land and returned to Norway in 1896.

Source label: `RGS` · [Historical reference](https://frammuseum.no/en/polar-history/expeditions/the-first-fram-expedition-1893-1896/).

*Date review: The mapped sledge leg from Fram toward Franz Josef Land began in March 1895, not 1894. The wider Fram expedition continued until 1896. [Reference](https://frammuseum.no/en/polar-history/expeditions/the-first-fram-expedition-1893-1896/).*

### 30. Amundsen — 1903–1906

Roald Amundsen sailed the small vessel Gjøa through the Canadian Arctic from 1903 to 1906, completing the first successful Northwest Passage voyage by a single ship. The crew overwintered near King William Island and gathered magnetic and geographic observations before reaching Alaska.

Source label: `RGS` · [Historical reference](https://www.rmg.co.uk/stories/maritime-history/roald-amundsen-north-west-passage-expedition-1903-06).

### 31. Peary — 1909

Robert Peary's 1909 expedition travelled north from Ellesmere Island by dog sledge across the Arctic sea ice, supported by a party that included Matthew Henson and Inuit explorers. Peary claimed to have reached the North Pole on 6 April 1909, but historians continue to debate whether the party actually attained the precise geographical pole.

Source label: `RGS` · [Historical reference](https://www.smithsonianmag.com/history/who-discovered-the-north-pole-116633746/).

### 32. Stefansson — 1913–1918

Vilhjalmur Stefansson led the northern party of the Canadian Arctic Expedition of 1913–1918, exploring Beaufort Sea waters and islands of the western Canadian Arctic. The expedition combined coastal surveys, scientific observations and extensive travel across sea ice, although it was also marked by serious hardships and losses.

Source label: `RGS` · [Historical reference](https://www2.whoi.edu/site/beaufortgyre/history/the-canadian-arctic-expedition-1913-1918/).

### 33. Nobile — 1926

Umberto Nobile commanded the airship Norge on the celebrated 1926 transpolar flight organized with Roald Amundsen and Lincoln Ellsworth. The aircraft passed over the North Pole after departing Svalbard and continued across the Arctic Ocean to Alaska, demonstrating the possibilities of long-range polar aviation.

Source label: `RGS` · [Historical reference](https://svalbardmuseum.no/en/amundsens-and-nobiles-airship-voyages).

### 34. Nobile — 1928

During the 1928 Italia expedition, Umberto Nobile made exploratory airship flights from the base at Ny-Ålesund on Svalbard. One major eastward flight passed the Franz Josef Land region toward Severnaya Zemlya before returning, extending aerial observations of the high Arctic.

Source label: `EGS UK` · [Historical reference](https://link.springer.com/article/10.1007/s00016-025-00338-9).

### 35. Nobile — 1928

In May 1928 Umberto Nobile flew the airship Italia from Svalbard to the North Pole and attempted to return to base. The airship crashed onto drifting pack ice northeast of Svalbard, triggering a major international rescue operation that saved several survivors but also resulted in further losses.

Source label: `RGS` · [Historical reference](https://svalbardmuseum.no/en/amundsens-and-nobiles-airship-voyages).

### 36. Herbert — 1968–1969

Wally Herbert led the British Trans-Arctic Expedition of 1968–1969 across the frozen Arctic Ocean by dog sledge, travelling from Alaska toward Svalbard. The four-man team passed through the North Pole in April 1969 and completed a pioneering surface crossing of the Arctic Ocean in May.

Source label: `RGS` · [Historical reference](https://www.guinnessworldrecords.com/world-records/67801-first-crossing-of-the-arctic).

## Authorship, citation and re-use

**By Bartolome Ortiz Viso**  
**Original reconstruction, descriptive compilation and interactive visualisation:** Creative Commons Attribution 4.0 International ([CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)). You may share and adapt these original contributions, including for commercial use, as long as you credit the author, link to the license and indicate changes. Suggested attribution:

> Bartolome Ortiz Viso, *Arctic Historical Expeditions — Interactive 3D Globe*, CC BY 4.0. [Link to project repository].

The historical maps, book material and externally sourced imagery may be subject to **separate rights**; this license does not grant rights the author does not own. The interactive globe's Solar System Scope Earth texture is credited to its creator and is available under **CC BY 4.0** (see its [Wikimedia Commons file page](https://commons.wikimedia.org/wiki/File:Solarsystemscope_texture_8k_earth_daymap.jpg)). Country and geographic data are presented for general orientation. Historical route lines should not be treated as modern navigational charts.

---

*Data reviewed: 22 November 2026. The original maps and field measurements were not independently re-georeferenced in this date-review update; only the year attributes, contextual descriptions and documentation were updated.*
