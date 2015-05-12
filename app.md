
## Responsive Page Implementation

Copyright 2015, Fauna, Inc. All rights reserved. For general instructions, see [here](https://github.com/faunadb/exercises/blob/master/README.md).

Consider the following pair of mockups:

<img src="https://raw.githubusercontent.com/faunadb/exercises/master/app.jpg" width="33%" style="float:left;">
<img src="https://raw.githubusercontent.com/faunadb/exercises/master/app2.jpg" width="33%" style="float:left;margin-left:10px;">

Your task is to implement this webpage as valid HTML, SCSS, and JavaScript.

Instructions:

  - The first mockup shows the original state of the page.
  - The second mockup shows the transition states of various elements on the page. The transitions are:
    - A functioning dropdown with collapsible `ul` and `li` elements within it.
    - A slider that covers the top area no matter the width
    - The third section with the pink icons, which appears on the screen when scrolled. They appear individually with initial state of half opacity, half scale.
    - The large image in the "Latest News" section, which flips a card to reveal the background and text underneath.
  - At the end of the third section with the pink icons, add the text "Where are you located in the United States?" with a `select` input for the user to choose their state. Please style it according to the rest of the page.

Requirements:

  - Do not use Bootstrap.
  - Your implementation should be responsive with clear breakpoints.
  - Use SMACSS with SCSS.
  - Include at least 3 different hover effects; two for text, and one for a call-to-action button.
  - Use [this SVG](https://github.com/faunadb/exercises/master/business-icon.svg) to create the second slider. It must be rendered as an SVG and scale responsively with its container.
  - Render the text within the SVG in the second slider underneath the triangle light layer. It must render precisely.
  - You must include automated tests for layout and behavior using a framework such as PhantomJS

Additional notes:

  - The body font-family is Open Sans; headings are Montserrat.
  - All icons can be replaced with whatever icons you choose.
  - All text can be lorem ipsum.
  - HiDPI images are not required.
