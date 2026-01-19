# Add Chart to Blog Post

Use this skill when the user asks to add a chart (bar, line, pie, etc.) to a distill blog post using Chart.js, ECharts, or Vega-Lite.

## Front Matter Required

Enable the chart library you want to use:

```yaml
chart:
  chartjs: true    # For Chart.js
  echarts: true    # For ECharts
  vega_lite: true  # For Vega-Lite
```

---

## Chart.js

Simple, clean charts. Good for basic visualizations.

### Bar Chart

~~~markdown
```chartjs
{
  "type": "bar",
  "data": {
    "labels": ["2020", "2021", "2022", "2023"],
    "datasets": [{
      "label": "Revenue (M)",
      "data": [12, 19, 15, 22],
      "backgroundColor": "rgba(54, 162, 235, 0.6)",
      "borderColor": "rgba(54, 162, 235, 1)",
      "borderWidth": 1
    }]
  },
  "options": {
    "scales": {
      "y": {"beginAtZero": true}
    }
  }
}
```
~~~

### Line Chart

~~~markdown
```chartjs
{
  "type": "line",
  "data": {
    "labels": ["Jan", "Feb", "Mar", "Apr", "May"],
    "datasets": [{
      "label": "Temperature",
      "data": [5, 8, 15, 18, 22],
      "borderColor": "rgb(75, 192, 192)",
      "tension": 0.1
    }]
  }
}
```
~~~

### Pie Chart

~~~markdown
```chartjs
{
  "type": "pie",
  "data": {
    "labels": ["Red", "Blue", "Yellow"],
    "datasets": [{
      "data": [300, 50, 100],
      "backgroundColor": ["#FF6384", "#36A2EB", "#FFCE56"]
    }]
  }
}
```
~~~

---

## ECharts

Feature-rich, highly customizable. Good for complex interactive charts.

### Line Chart with Area

~~~markdown
```echarts
{
  "title": {"text": "Monthly Sales", "left": "center"},
  "tooltip": {"trigger": "axis"},
  "xAxis": {
    "type": "category",
    "data": ["Jan", "Feb", "Mar", "Apr", "May", "Jun"]
  },
  "yAxis": {"type": "value"},
  "series": [{
    "name": "Sales",
    "type": "line",
    "smooth": true,
    "data": [820, 932, 901, 934, 1290, 1330],
    "areaStyle": {
      "color": {
        "type": "linear",
        "x": 0, "y": 0, "x2": 0, "y2": 1,
        "colorStops": [
          {"offset": 0, "color": "rgba(84, 112, 198, 0.5)"},
          {"offset": 1, "color": "rgba(84, 112, 198, 0)"}
        ]
      }
    }
  }]
}
```
~~~

### Multiple Series

~~~markdown
```echarts
{
  "legend": {"data": ["Product A", "Product B"]},
  "xAxis": {"type": "category", "data": ["Q1", "Q2", "Q3", "Q4"]},
  "yAxis": {"type": "value"},
  "series": [
    {"name": "Product A", "type": "bar", "data": [120, 200, 150, 80]},
    {"name": "Product B", "type": "bar", "data": [90, 170, 130, 100]}
  ]
}
```
~~~

---

## Vega-Lite

Declarative grammar, highly expressive. Good for statistical visualizations.

### Bar Chart

~~~markdown
```vega_lite
{
  "$schema": "https://vega.github.io/schema/vega/v5.json",
  "width": 400,
  "height": 200,
  "data": [{
    "name": "table",
    "values": [
      {"category": "A", "value": 28},
      {"category": "B", "value": 55},
      {"category": "C", "value": 43}
    ]
  }],
  "scales": [
    {"name": "xscale", "type": "band", "domain": {"data": "table", "field": "category"}, "range": "width", "padding": 0.1},
    {"name": "yscale", "type": "linear", "domain": {"data": "table", "field": "value"}, "nice": true, "range": "height"}
  ],
  "axes": [
    {"orient": "bottom", "scale": "xscale"},
    {"orient": "left", "scale": "yscale"}
  ],
  "marks": [{
    "type": "rect",
    "from": {"data": "table"},
    "encode": {
      "enter": {
        "x": {"scale": "xscale", "field": "category"},
        "width": {"scale": "xscale", "band": 0.8},
        "y": {"scale": "yscale", "field": "value"},
        "y2": {"scale": "yscale", "value": 0},
        "fill": {"value": "steelblue"}
      },
      "update": {"fillOpacity": {"value": 1}},
      "hover": {"fill": {"value": "orange"}}
    }
  }]
}
```
~~~

---

## Which to Choose?

| Library | Best For | Complexity |
|---------|----------|------------|
| Chart.js | Simple, quick charts | Low |
| ECharts | Rich interactive charts | Medium |
| Vega-Lite | Statistical/declarative charts | Medium-High |

## Notes

- All charts are interactive (hover effects, tooltips)
- Charts are responsive and resize with the container
- Use descriptive titles and axis labels
- Test color schemes for accessibility
