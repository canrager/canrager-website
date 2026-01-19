# Add Leaflet Map to Blog Post

Use this skill when the user asks to add an interactive map to a distill blog post using Leaflet.

## Front Matter Required

Enable map in the post's front matter:

```yaml
map: true
```

## Syntax

Use a fenced code block with `geojson` language identifier:

~~~markdown
```geojson
{
  "type": "FeatureCollection",
  "features": [
    {
      "type": "Feature",
      "properties": {
        "name": "Location Name",
        "popupContent": "Info shown on click"
      },
      "geometry": {
        "type": "Point",
        "coordinates": [longitude, latitude]
      }
    }
  ]
}
```
~~~

## Geometry Types

### Point (Marker)

```json
{
  "type": "Feature",
  "properties": {"name": "Berlin"},
  "geometry": {
    "type": "Point",
    "coordinates": [13.405, 52.52]
  }
}
```

### Polygon (Region)

```json
{
  "type": "Feature",
  "properties": {"name": "Region A"},
  "geometry": {
    "type": "Polygon",
    "coordinates": [[
      [lon1, lat1],
      [lon2, lat2],
      [lon3, lat3],
      [lon1, lat1]
    ]]
  }
}
```

Note: Polygon coordinates must form a closed ring (first and last point identical).

### LineString (Path)

```json
{
  "type": "Feature",
  "properties": {"name": "Route"},
  "geometry": {
    "type": "LineString",
    "coordinates": [
      [lon1, lat1],
      [lon2, lat2],
      [lon3, lat3]
    ]
  }
}
```

## Complete Example

~~~markdown
```geojson
{
  "type": "FeatureCollection",
  "features": [
    {
      "type": "Feature",
      "properties": {
        "name": "Berlin",
        "popupContent": "Capital of Germany"
      },
      "geometry": {
        "type": "Point",
        "coordinates": [13.405, 52.52]
      }
    },
    {
      "type": "Feature",
      "properties": {
        "name": "Munich",
        "popupContent": "Capital of Bavaria"
      },
      "geometry": {
        "type": "Point",
        "coordinates": [11.582, 48.139]
      }
    }
  ]
}
```
~~~

## Highlighting a Region

~~~markdown
```geojson
{
  "type": "FeatureCollection",
  "features": [
    {
      "type": "Feature",
      "properties": {
        "name": "Study Area",
        "popupContent": "Research was conducted in this region"
      },
      "geometry": {
        "type": "Polygon",
        "coordinates": [[
          [8.0, 47.0],
          [15.0, 47.0],
          [15.0, 55.0],
          [8.0, 55.0],
          [8.0, 47.0]
        ]]
      }
    }
  ]
}
```
~~~

## Notes

- Coordinates are in [longitude, latitude] format (not lat, lon!)
- Uses OpenStreetMap tiles as base layer
- Click on features to see popup content
- Map auto-zooms to fit all features
- GeoJSON data can be obtained from tools like [geojson.io](https://geojson.io)
