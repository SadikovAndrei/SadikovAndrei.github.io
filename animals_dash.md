## Building endangered species dash using Python PLotly Dash and GeoPandas
<img src="images/dash_thumbnail.png?raw=true"/>
**Project description:** For preprocessing data I used python with geopandas library:
1. Downloaded the files from The Environmental Conservation Online System file
with USA endangered species’ ranges
2. Cleaned the data
3. Using wikipedia API I’ve retreated picture links and descriptions for species
4. Then created intersection table with states for each species (I’ve done it with help of
comparing polygons from the dataset to polygons from geojson file with counties)
5. Interesting features: I’ve added the self-adjusting zoom to zoom in on polygons of
species ranges; The States map on Dash is added for the better spatial navigation

```python
import pandas as pd
import geopandas as gpd
import requests
import re
```

The Dashboard is launched on free hosting, so it takes significant time to load [OnRender](https://us-endangered-species-1.onrender.com).
