# British Airways Customer Review Analysis Dashboard

## Project Overview

This project showcases the creation of an interactive dashboard using Tableau to analyze British Airways customer reviews. The dashboard allows users to dynamically explore review data by selecting various metrics (overall rating, cabin staff service, food, etc.), applying filters (date, seat type, traveler type, aircraft, continent), and interacting directly with visualizations. Key features include an interactive map displaying average metric scores by country, summary metrics at the top for quick insights, a trend line chart showing average metric performance over time, and a bar chart comparing average metric scores by aircraft type. The project highlights skills in data connection, calculated fields, parameters, geographic visualization, interactive filtering, and dashboard design.

https://github.com/user-attachments/assets/df79fe8a-167e-4cfa-b102-468cf4c7a79a

## Process Breakdown

### 1. Data Connection and Preparation

* Connected to two CSV files: "BA Reviews" (containing individual reviews) and "Countries" (a country mapping table).
* Established a relationship between the two tables, linking the "place" column in "BA Reviews" to the "country" column in "Countries" to enable continent and region filtering.

### 2. Interactive Map Creation

* Converted the "place" field to a geographic role (country/region).
* Created a parameter called "Pick a Metric" with a list of string values representing the different review metrics (overall rating, cabin staff service, etc.). This parameter allows users to choose which metric to display on the map.
* Created a calculated field called "Metric Selected" using a CASE statement. This field dynamically selects the appropriate metric based on the value chosen in the "Pick a Metric" parameter.
* Dragged the "place" field to the Detail shelf to generate the map.
* Dragged the "Metric Selected" calculated field to the Color shelf to visualize the chosen metric on the map. Used the average aggregation.
* Customized the map's appearance (background layers, coastline, color palette).
* Created a dynamic title for the map, incorporating the selected metric.
* Added a tooltip to the map showing the place, average selected metric, and number of reviews. Formatted the tooltip and the average metric to one decimal place.

### 3. Filter Creation

* Created various filters based on the available data:
    * **Month:** Dragged the "date" field to the Filters shelf and configured it as a continuous month filter.
    * **Seat Type:** Dragged the "seat_type" field to the Filters shelf and configured it as a single-value list.
    * **Traveler Type:** Dragged the "traveller_type" field to the Filters shelf and configured it as a single-value list. Handled the null value.
    * **Aircraft:** Dragged the "aircraft" field to the Filters shelf. Grouped aircraft with fewer than 50 reviews into a "Various" category. Configured the filter as a single-value dropdown.
    * **Continent:** Dragged the "continent" field (from the "Countries" table) to the Filters shelf and configured it as a single-value dropdown.
* Applied all filters to all worksheets using the "All using this data" option.
* Arranged the filters in a vertical container on the dashboard.

### 4. Summary Metrics Creation

* Created a new worksheet.
* Dragged the various rating metrics (overall rating, cabin staff service, etc.) to the Text Marks Card, using the average aggregation.
* Dragged "Measure Names" to the Columns shelf and "Measure Values" to the Text Marks Card to display the metrics horizontally.
* Formatted the text (alignment, font size, boldness).
* Removed the header and renamed the sheet to "Summary."
* Reordered the summary metrics, placing "Average Rating" first.
* Formatted the decimals in the summary metrics to one decimal place.
* Removed row dividers in the summary table.

### 5. Average Metric by Month Chart Creation

* Created a new worksheet.
* Dragged the "date" field to the Columns shelf and configured it as a continuous month.
* Dragged the "Metric Selected" calculated field to the Rows shelf, using the average aggregation.
* Applied the chosen green color to the line.
* Customized the chart's appearance (removed grid lines, axis titles, and borders).
* Created a dynamic title for the chart.
* Formatted the tooltip to display the selected metric and removed unnecessary information.

### 6. Average Metric by Aircraft Chart Creation

* Created a new worksheet.
* Dragged the "aircraft_group" field to the Rows shelf.
* Dragged the "Metric Selected" calculated field to the Columns shelf, using the average aggregation. Sorted in descending order.
* Dragged the COUNTD(review_id) to the Columns shelf, creating a dual-axis chart. This shows the number of reviews for each aircraft group.
* Renamed the axes appropriately (using the parameter name for the metric axis).
* Customized the chart's appearance (removed dividers, borders, and field labels).
* Applied colors to the bars (green for the metric and pink for the number of reviews). Corrected the color scaling for the number of reviews.
* Added data labels to the bars, formatted to one decimal place for the metric.
* Customized the tooltips for both bars, ensuring clarity and removing redundancies.

### 7. Dashboard Assembly

* Created a new dashboard with a fixed size.
* Added a title to the dashboard.
* Added the "Summary" sheet to the dashboard.
* Added the "Map" sheet and positioned it below the summary metrics.
* Added all the created filters to a vertical container on the left side of the dashboard.
* Added the "Month" chart and the "Aircraft" chart to the dashboard, arranging them appropriately.
* Adjusted the sizes and positions of all elements to create a visually appealing layout.
* Added a green separator line between the filters and the main dashboard area.
* Configured the map, month chart, and aircraft chart to act as filters for the other views using the "Use as Filter" option.

### 8. Dashboard Testing and Refinement

* Tested all filters and interactions to ensure they functioned correctly.
* Reviewed and refined tooltips for all visualizations.
* Made final adjustments to the layout and formatting.

## Summary

This British Airways review dashboard provides a comprehensive and interactive way to explore customer feedback. By dynamically selecting metrics, applying filters, and interacting with the visualizations, users can easily identify trends, understand customer sentiment, and gain valuable insights into various aspects of the airline's service. This project effectively demonstrates the power of Tableau in creating engaging and informative dashboards for data analysis.
