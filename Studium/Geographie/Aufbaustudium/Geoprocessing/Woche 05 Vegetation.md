> [!Recap Woche 4]
> - NDSI $\frac{VIS-NIR}{VIS+NIR}>0.4$ liegt Schnee
> - Korngrösse von Schnee (je älter desto grösser) reduziert die Reflektanz im nahen Infrarotbereich

**Motivation**

- Vegetationsentwicklung im Jahresgang (Landwirtschaft/ climate change)
- Überwachung von Wasserstress
- Überwachung von Pflanzenkrankeiten ( z.B. Waldsterben oder Pilzbefall)
- Notwendige Information für die Wettervorhersage (Blattflächenindex; Grad der Vegetationsbedeckung)
- Verschiebung von Vegetationsgürtel
- Überwachung des Amazonas Regenwald
- Ernteschätzung
- …..

## Normalized Differential Vegetation Index [[NDVI]]

- Reflektanz von Vegetation im nahen Infrarot relativ hoch
- Temp sinkt da Energie für Evapotranspiration gebraucht wird
![[Pasted image 20231017084255.png]]
- Im sichtbaren Bereich ist die reflektanz sehr gering
	- Kleiner peak im grünen Bereich
	- Trockene Vegetation hat eine höhere Reflektanz im sichtbaren Bereich, besonders starker Anstieg im roten Bereich
- Im nahen Infrarot ist die Differenz zwischen grüner Vegetation und trockener Vegetation stark.
	- Wasserdruck in den Zellen nimmt ab
	- Zellstruktur ändert sich
	- Reflektanz sinkt
- Im sichtabren Bereich wird es schwierig Boden von trockener Vegetation zu unterscheiden. Im nahen Infrarot weiterhin möglich
- Reflektanzkurve ist für verschiedene Vegetationsarten sehr ähnlich. Absolutwerte ändern sich etwas, aber Verlauf ist fast universell
- ![[Pasted image 20231017084950.png]]
- Reflektanz kann sich auch wegen der Vegetationsbedeckung und kaum wegen Trockenstress
- Mitlicht und Gegenlicht
- ![[Pasted image 20231017090020.png]]
	- In Abhängigkeit vom Sonnenstand ändert sich die Reflektanz
	- Sateliten sind in einem Sonnensynchronen Orbit, um diese Fehlerquelle zu minimieren (d.H. ein Landsat Satelit fliegt bspw. alle zwei Wochen immer um 10:00 Uhr über Bern)
## Berechnung

> [!Important]
> $$NDVI= \frac{NIR - VIS}{NIR + VIS} \rightarrow \frac{TM_4 - TM_3}{TM_4 + TM_3}$$
> - Wertebereich  $-1 \leq NDVI \leq 1$
> 	- $-1 \rightarrow$ Keine Vegetation
> 	- $1 \rightarrow$ Volle Vegetation
> - Verschiedene Aktivitätszonen (hier Beispielhaft für die Übung)
> 	- $NDVI \ge 0.6$
> 	- $0.4 \leq NDVI \leq 0.59$
> 	- $0.2 \leq NDVI \leq 0.39$
> 	- $NDVI < 0.2$
> - SAVI (soil adjusted Vegetation index)
> 	- $$SAVI= \frac{NIR - VIS}{NIR + VIS} \cdot (1 + L) \rightarrow \frac{TM_4 - TM_3}{TM_4 + TM_3} \cdot (1 + L)$$
> 		- L: Parameter der den Grad der Vegetationsbedeckung beschreibt
> 			- $L=0 \rightarrow$ starke Vegetationsbedeckung (SAVI = NDVI)
> 			- $L=1 \rightarrow$ geringe Vegetationsbedeckung
> 		- Paramter kaum effizient für jedes Pixel zu bestimmen, wird auch nur selten entsprechend angewendet
 

- Kann bspw. verwendet werden um in hoher Auflösung früh Erkrankungen zu bemerken und entsprechend zu bekämpfen

