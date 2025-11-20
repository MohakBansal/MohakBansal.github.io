---
layout: default
title: "HW5 – Building Inventory Visualizations"
---

# HW5 – Building Inventory Visualizations

## Links
[**The Data**](https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/building_inventory.csv){:target="_blank"}  
[**The Analysis (Notebook)**](https://github.com/MohakBansal/is445-hw5/blob/main/Workbook.ipynb){:target="_blank"}

---

## Plot 1: Top Agencies by Total Square Footage

<p>The first plot summarizes which Illinois agencies manage the most building space. To create this visualization, I used Python to group the building inventory data by agency and sum the “Square Footage” field, then filtered to the top ten agencies by total square footage so the y-axis stays readable. In the Altair chart, I encoded total square footage as a quantitative variable on the x-axis and agency names as a nominal variable on the y-axis, sorted in descending order by size so the most space-intensive agencies appear at the top. Color is mapped to the total square footage using a sequential colormap, reinforcing the magnitude differences. This makes it easy to compare which agencies dominate the state’s building footprint.</p>

<div id="plot1"></div>

---

## Plot 2: Total Square Footage by Construction Decade (Interactive by Usage)

<p>The second plot examines how building square footage is distributed across construction decades for different usage types. I created a decade column, aggregated total square footage per decade and usage category, and restricted the plot to the top usage classifications to avoid clutter. I encoded decade on the x-axis, square footage on the y-axis, and used color to distinguish decades. Tooltips provide additional detail. These transformations reveal patterns in how facility types were built across history.</p>

<p>The interactivity uses an Altair parameter bound to a dropdown. Changing the selection filters the chart to display only the chosen usage type. This goes beyond pan/zoom by letting viewers actively choose a subset, making the visualization clearer and more exploratory.</p>

<div id="plot2"></div>

---

<!-- Vega / Vega-Lite / Vega-Embed -->
<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script type="text/javascript">
  vegaEmbed("#plot1", "{{ '/assets/json/plot1.json' | relative_url }}");
  vegaEmbed("#plot2", "{{ '/assets/json/plot2.json' | relative_url }}");
</script>
