
## UX Exercise

Copyright 2015, Fauna, Inc. All rights reserved. For general instructions, see [here](https://github.com/faunadb/exercises/blob/master/README.md).

### Responsive Visualization

Consider the following dataset provided by the USDA ([Excel format](https://raw.githubusercontent.com/faunadb/exercises/master/visualization/importedfoodsbycountry2015.xls) / [HTML format](https://raw.githubusercontent.com/faunadb/exercises/master/visualization/importedfoodsbycountry2015.tar.gz)) of food import quantities to the United States by year, category, and origin.

One way to visualize this data might be:

<img src="https://raw.githubusercontent.com/faunadb/exercises/master/visualization/visualization.jpg" width="50%">

But this way is terrible.

Your goal is to present this data in a way that makes sense and allows for exploration.

  - For **product designers**, you should create mockups for all views and interaction elements, including desktop and mobile layouts. Assume a responsive design and implementation.
  - For **front-end engineers**, implement a responsive webpage with valid HTML, CSS, and JavaScript.

Include a written discussion of the user experience of the page and the design decisions you made in light of the user's needs. Note that the units for each category are not always the same. You'll need to find a way to either normalize all units, or prevent comparisons that don't make sense.

The original data sources are [here](http://www.ers.usda.gov/data-products/us-food-imports.aspx).

#### General requirements

  - The visualization should support drilldown by category, year, and country of origin. Present data excluded from the drilldown as an aggregation to add context if it makes sense.
  - The layout should be responsive and work on both desktop and mobile. The desktop layout should be 950px wide.
  - Use a consistent palette and font set.
  - If you obscure any items in dropdowns, accordions, or the like, implement or show the expanded view as well.

#### Additional design requirements

  - Include some icons with a consistent visual language.
  - Include an original logo or illustration.
  - Include a photograph as a background element.
  - Include a call-to-action button.

#### Additional front-end requirements

  - Do not use Bootstrap.
  - Use a visualization framework such as D3 and interpret an embedded dataset that can be easily updated.
  - Include automated tests for layout or behavior using a framework such as PhantomJS or Galen.
  - Include some animation effects.

#### Extra credit

Fulfill as much of the criteria from the other role as possible: designers, implement a responsive webpage of your design. Front-end engineers, include some of the requested design elements in your webpage.
