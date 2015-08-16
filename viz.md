
## Responsive visualization exercise

Copyright 2015, Fauna, Inc. All rights reserved. For general instructions, see [here](https://github.com/faunadb/exercises/blob/master/README.md).

Consider the following dataset provided by the USDA ([Excel format](https://raw.githubusercontent.com/faunadb/exercises/master/viz/importedfoodsbycountry2015.xls) / [HTML format](https://raw.githubusercontent.com/faunadb/exercises/master/viz/importedfoodsbycountry2015.tar.gz)) of food import quantities to the United States by year, category, and origin.

One way to visualize this data might be:

<img src="https://raw.githubusercontent.com/faunadb/exercises/master/viz/viz.jpg" width="50%">

But this way is terrible.

Your goal is to present this data in a way that makes sense and allows for exploration. Your visualization should implemented as a single webpage with valid HTML, CSS, and JavaScript.

The original data sources are [here](http://www.ers.usda.gov/data-products/us-food-imports.aspx).

Requirements:

  - You should use a visualization framework such as D3 and interpret an embedded dataset that can be easily updated.
  - The visualization should be interactive.
  - The visualization should support drilldown by category, year, and country of origin.
  - The layout should be responsive and work on both desktop and mobile.
  - Include automated tests for layout or behavior using a framework such as PhantomJS or Galen.
  - Do not use Bootstrap.

Additional notes:

  - The units for each category are not the same. You should find a way to either normalize all units, or prevent comparisons and aggregations that don't make sense.

### Extra credit

  - Aggregate any data excluded from the current selection and present the aggregation along with the selected data to add context.
  - Include some animation effects.
