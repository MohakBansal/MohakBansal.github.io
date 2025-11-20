---
layout: default
title: "HW5 – Building Inventory Visualizations"
---

# HW5 – Building Inventory Visualizations

## Links

<p>
  <a class="btn" href="https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/building_inventory.csv" target="_blank">
    The Data
  </a>
</p>

<p>
  <a class="btn" href="https://github.com/MohakBansal/MohakBansal.github.io/blob/main/python_notebooks/Workbook.ipynb" target="_blank">
    The Analysis (Notebook)
  </a>
</p>

---

## Plot 1: Top Agencies by Total Square Footage

<p>
The first plot summarizes which Illinois agencies manage the most building space. To create this visualization, I grouped the building inventory data by agency and summed the “Square Footage” field, then filtered to the top ten agencies by total square footage so the y-axis remains readable. The bar chart encodes total square footage as a quantitative x-axis, and agency names as a nominal y-axis sorted in descending order. I used a sequential colormap to reinforce the magnitude differences. These transformations and encoding choices make it easy to compare which agencies control the most building area across the state.
</p>

<div id="plot1"></div>

---

## Plot 2: Total Square Footage by Construction Decade (Interactive by Usage)

<p>
The second plot shows how building space is distributed across construction decades for different usage types. I converted the “Year Constructed” column into numeric, filtered unrealistic values, and created a “decade” field by flooring years to the nearest decade. I then aggregated total square footage per decade and usage description, limiting the visualization to the top usage categories for clarity. The bar chart encodes decade on the x-axis, total square footage on the y-axis, and colors bars by decade. Tooltips reveal decade, usage type, and square footage.
</p>

<p>
The plot includes a dropdown parameter that filters the chart by usage category. When the user selects a usage type, only buildings of that type are shown across decades. This interactivity goes beyond pan/zoom by allowing viewers to explore patterns category-by-category, avoiding clutter and making it easier to understand construction trends for specific building purposes.
</p>

<div id="plot2"></div>

---

<!-- Vega Libraries -->
<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<!-- Embed JSON Plots -->
<script type="text/javascript">
  vegaEmbed("#plot1", "{{ '/assets/json/plot1.json' | relative_url }}");
  vegaEmbed("#plot2", "{{ '/assets/json/plot2.json' | relative_url }}");
</script>
