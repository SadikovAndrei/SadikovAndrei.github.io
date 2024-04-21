## Building endangered species dash using Python PLotly Dash and GeoPandas
<img src="images/dash_thumbnail.png?raw=true"/>
**Project description:** This is an interactive dashboard showcasing some endangered species of the USA with treir habitat and a desription.
## 1. Downloaded the files from The Environmental Conservation Online System file with USA endangered species’ ranges
## 2. Cleaned the data
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
    data = response.json()
```
## 4. Then created intersection table with states for each species (I’ve done it with help of
comparing polygons from the dataset to polygons from geojson file with counties)
## 5. Interesting features: I’ve added the self-adjusting zoom to zoom in on polygons of
species ranges; The States map on Dash is added for the better spatial navigation

```python
import pandas as pd
import geopandas as gpd
import requests
import re
```

The Dashboard is launched on free hosting, so it takes a significant time to load [OnRender](https://us-endangered-species-1.onrender.com).
