# Add Interactive Plot to Blog Post

Use this skill when the user asks to add an interactive plot (using Plotly) to a distill blog post.

## Overview

Interactive plots are embedded via iframes. The plot must be generated separately and saved as an HTML file.

## Steps

### 1. Create the Plot

Generate a Plotly figure and save it as HTML:

```python
import pandas as pd
import plotly.express as px

# Example: earthquake density map
df = pd.read_csv('https://raw.githubusercontent.com/plotly/datasets/master/earthquakes-23k.csv')
fig = px.density_mapbox(
    df,
    lat='Latitude',
    lon='Longitude',
    z='Magnitude',
    radius=10,
    center=dict(lat=0, lon=180),
    zoom=0,
    mapbox_style="stamen-terrain",
)
fig.write_html('assets/plotly/my_plot.html')
```

### 2. Save the HTML File

Save the plot to `assets/plotly/` directory:
- Create directory if needed: `assets/plotly/`
- Use descriptive filename: `my_plot.html`, `earthquake_map.html`, etc.

### 3. Embed in Blog Post

Use an iframe with the `l-page` class for full-width display:

```html
<div class="l-page">
  <iframe src="{{ '/assets/plotly/my_plot.html' | relative_url }}" frameborder='0' scrolling='no' height="500px" width="100%" style="border: 1px dashed grey;"></iframe>
</div>
```

## Layout Options

| Class | Width |
|-------|-------|
| `l-body` | Standard text width |
| `l-page` | Wider, page width |
| `l-screen` | Full browser width |

## Example: Simple Line Chart

```python
import plotly.express as px

df = px.data.gapminder().query("country=='United States'")
fig = px.line(df, x='year', y='gdpPercap', title='US GDP per Capita')
fig.write_html('assets/plotly/us_gdp.html')
```

Embed:
```html
<div class="l-page">
  <iframe src="{{ '/assets/plotly/us_gdp.html' | relative_url }}" frameborder='0' scrolling='no' height="400px" width="100%"></iframe>
</div>
```

## Notes

- Adjust `height` attribute based on your plot dimensions
- Remove `scrolling='no'` if the plot needs scroll functionality
- The `relative_url` filter ensures correct paths in production
