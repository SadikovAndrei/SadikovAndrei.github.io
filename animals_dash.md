## Building endangered species dash using Python PLotly Dash and GeoPandas
<img src="images/dash_thumbnail.png?raw=true"/>
**Project description:** This is an interactive dashboard showcasing some endangered species of the USA with treir habitat and a description.
## 1. Downloaded the files from The Environmental Conservation Online System file with USA endangered species’ ranges
```python
source= 'https://ecos.fws.gov/ecp/report/table/critical-habitat.html#:~:text=A-,zip%20file,-containing%20two%20shapefiles'
```
## 2. Cleaned the data
Dropped not useful columns, duplicates.
```python
#Excluding some values that either don't have picture or don't have a correct habitat
values_to_exclude = ['Chelonia mydas', 'Etheostoma phytophilum', 'Corvus kubaryi', 'Lepidomeda vittata', 'Catostomus warnerensis', 'Charadrius nivosus nivosus', 'Rana muscosa','Zosterops rotensis']
gdf = gdf[~gdf['sciname'].isin(values_to_exclude)]
#dropping  duplicate values
gdf.drop_duplicates(subset=None, keep='first', inplace=True)
```
## 3. Using wikipedia API I’ve retreated picture links and descriptions for species
```python
# Using wikipedia API retrieving image links
for i,row in enumerate(list_names):
    page_title = list_names[i]

    url = 'https://en.wikipedia.org/w/api.php'
    params = {
    'action': 'query',
    'format': 'json',
    'redirects': '1',
    'titles': page_title
    }
    response = requests.get(url, params=params)
    data = response.json()...
```
## 4. I've decided to create a second map showing zoom-out in which states is a habitat located. So I created an intersection table with states for each species
I’ve done it with help of comparing polygons from the dataset to polygons from geojson file with States outlines
```python
intersection_gdf = gpd.sjoin(gdf, states_gdf, how="inner", predicate='intersects')
```

## 5. Interesting features: I’ve added the self-adjusting zoom to zoom in on polygons of
species ranges; The States map on Dash is added for the better spatial navigation

```python
def update_input_container(value):
    
    
    
    df1 = gdf[gdf['sciname'] == value]
    
    poly = df1['geometry']
    poly = poly.iloc[0]  # Access the first polygon
    centroid = poly.centroid
    centroid_x, centroid_y = centroid.y, centroid.x  # Reversed for correct lat-lon assignment
    center = {"lat": centroid_x, "lon": centroid_y}
    if poly.area >= 500:
        zoom = 0 ...
```

The Dashboard is launched on a free hosting, so it takes a significant time to load [OnRender](https://us-endangered-species-1.onrender.com).
