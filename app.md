
## Responsive layout exercise

Copyright 2015, Fauna, Inc. All rights reserved. For general instructions, see [here](https://github.com/faunadb/exercises/blob/master/README.md).

Consider the following pair of mockups:

<img src="https://raw.githubusercontent.com/faunadb/exercises/master/app/app.jpg" width="33%" style="float:left;">
<img src="https://raw.githubusercontent.com/faunadb/exercises/master/app/app2.jpg" width="33%" style="float:left;margin-left:10px;">

Your goal is to implement this webpage as valid HTML, SCSS, and JavaScript.

Instructions:

  - The first mockup shows the original state of the page.
  - The second mockup shows the transition states of various elements on the page:
    - The dropdown should function, with collapsible `ul` and `li` elements within it.
    - The slider should cover the top area no matter the width.
    - The pink icons in the third section should begin with an initial state of half opacity, half scale, and expand and increase in opacity when they scroll into view.
    - The large image in the "Latest News" section should flip a card to reveal the background and text underneath.
  - At the end of the third section with the pink icons, add the text "Where are you located in the United States?" with a `select` input for the user to choose their state. Please style it according to the rest of the page.

Requirements:

  - Your implementation should be responsive with clear breakpoints, and scale to desktop, tablet, and mobile viewports.
  - Use SMACSS with SCSS.
  - Include at least 3 different hover effects; two for text, and one for a call-to-action button.
  - Use [this SVG](https://github.com/faunadb/exercises/blob/master/app/business-icon.svg) to create the second slider. It must be rendered as an SVG and scale responsively with its container.
  - Include automated tests for layout and/or behavior using a framework such as PhantomJS or Galen.
  - Do not use Bootstrap.

Additional notes:

  - The body font-family is Open Sans; headings are Montserrat.
  - All icons can be replaced with whatever icons you choose.
  - All text can be lorem ipsum.
  - HiDPI images are not required.

### Extra credit

  - Render the text within the SVG in the second slider underneath the triangle light layer. It must render precisely.
