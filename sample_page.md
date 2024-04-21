## Building endangered species dash using Python PLotly Dash and Pandas

**Project description:** For preprocessing data I used python with geopandas library:
1. Downloaded the files from The Environmental Conservation Online System file
with USA endangered species’ ranges
2. Cleaned the data
3. Using wikipedia API I’ve retreated picture links and descriptions for species
4. Then created intersection table with states for each species (I’ve done it with help of
comparing polygons from the dataset to polygons from geojson file with counties)
5. Interesting features: I’ve added the self-adjusting zoom to zoom in on polygons of
species ranges; The States map on Dash is added for the better spatial navigation

### 1. Suggest hypotheses about the causes of observed phenomena

Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. 

```python
import pandas as pd
import geopandas as gpd
import requests
import re
```

### 2. Assess assumptions on which statistical inference will be based

```javascript
if (isAwesome){
  return true
}
```

### 3. Support the selection of appropriate statistical tools and techniques

<img src="images/dash_thumbnail.png?raw=true"/>

### 4. Provide a basis for further data collection through surveys or experiments

Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. 

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).
