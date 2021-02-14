# Regional Glacier Hypsometry with Self-Organizing Maps

Using a self-organizing map to cluster normalized glacier hypsometry, we can investigate (1) how the map 'thinks' or 'organizes', and (2) how glacier hypsometries vary in both real- and map- space.

Code:
* glacier_hypso.ipynb: Load data, make SOM, visualize results

Data:
* RGI: Glacier shapefiles/hypsometry from the the [Randolph Glacier Inventory V6.0](https://www.glims.org/RGI/)
* PROVINCE.SHP: [Provincial boundaries in Canada] (https://www.sciencebase.gov/catalog/item/50db7765e4b061270600bc02)
* teulingfig2.png: [2D colourmap for SOM visualization] (https://github.com/dominikjaeckle/Color2D)

___
## Example

Using an 8x8 map, the normalized hypsometry can be clustered onto the following SOM:

<img src="https://github.com/andersonsam/glacier_hypso_SOM/blob/main/Figures/SOM_patterns.png" width="700" />

We can see that the SOM generally organizes hypsometries by having the lowest elevation glaciers in the bottom left, with increasing mean elevation counter-clockwise around the border.  Glaciers which span a larger elevation range are pulled more to the middle of the map, while 'bi-modal' glaciers (e.g. a disconnected glacier, with two potentially-separate ice covered areas) are pulled to the centre-left region of the map.

Assigning each BMU a colour from a 2D colourmap, we can visualize the spatial distribution of BMUs:

<img src="https://github.com/andersonsam/glacier_hypso_SOM/blob/main/Figures/BMUs_whole_region.png" width="700" />

Now let's investigate how BMUs vary across sub-regions.

<img src="https://github.com/andersonsam/glacier_hypso_SOM/blob/main/Figures/BMUs_BC.png" width="700" />

Along the southern coast in British Columbia, BMUs change from ~orange to ~dark blue along a northeastern path inland crossing the coast mountain range.  On the SOM, this is a path from the bottom-right corner to the upper-right corner, indicating generally increasing glacier elevation from the western-to-eastern slopes.

<img src="https://github.com/andersonsam/glacier_hypso_SOM/blob/main/Figures/BMUs_AB.png" width="700" />

In comparison in the Albertan Rocky Mountains, BMUs change from ~dark blue to ~light blue along a northeastern path across the mountain range.  On the SOM, this is a path from the upper-right corner to the upper-left corner, again indicating a generally increasing glacier elevation from the western-to-eastern slopes.

<img src="https://github.com/andersonsam/glacier_hypso_SOM/blob/main/Figures/BMUs_AK.png" width="700" />

Alaska is a bit different, with the most coastal glaciers being sorted into the center of the SOM, with glaciers which span a wider range of elevations or having bi-model area-elevation distributions.  Moving inland, glaciers sort from lower to higher elevations on the SOM (bottom left to upper-right, counterclockwise on SOM).

[AB]: https://github.com/andersonsam/glacier_hypso_SOM/blob/main/Figures/BMUs_AB.png
[BC]: https://github.com/andersonsam/glacier_hypso_SOM/blob/main/Figures/BMUs_BC.png
[AK]: https://github.com/andersonsam/glacier_hypso_SOM/blob/main/Figures/BMUs_AK.png
[region]: https://github.com/andersonsam/glacier_hypso_SOM/blob/main/Figures/BMUs_whole_region.png
[SOM]: https://github.com/andersonsam/glacier_hypso_SOM/blob/main/Figures/SOM_patterns.png
___
## Requirements:

The code is written using Python 3.7.1 and uses the following libraries:
* minisom
* cartopy
* geopandas
* pandas
* numpy
* matplotlib

