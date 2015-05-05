
## App

Copyright 2015, Fauna, Inc. All rights reserved. For general instructions, see [here](https://github.com/faunadb/exercises/blob/master/README.md).

Consider the following mockups:

<img src="https://raw.githubusercontent.com/faunadb/exercises/master/app.jpg" width="25%" style="float:left;">
<img src="https://raw.githubusercontent.com/faunadb/exercises/master/app2.jpg" width="25%" style="float:left;margin-left:10px;">

Your task is to implement it as single webpage with valid HTML, SCSS, and JavaScript.

Instructions:

  - The first mockup shows the original state of the page.
  - The second mockup shows the transition states of various elements on the page.
  - Transitions: 
    - Functioning dropdown with collapsible ul, li elements within it
    - Slider that covers the top area no matter the width
    - The third section with all of the pink icons must appear on the screen with scroll. They must individually appear with initial state of half opacity, half scale.
    - The large image in "Latest News" section must flip like a card to reveal the background and text underneath
  - At the end of the third section with all of the icons, add the text "Where are you located in the United States?" with a select input where the user can choose their state of residence and style it according to the page.

Requirements:

  - The implementation must be responsive, with clear breakpoints.
  - Navigation dropdowns must function and be implemented with JavaScript.
  - Do not use Bootstrap.
  - Include at least 3 different hover effects; two for text, and one for a CTA button.
  - Use SMACSS, with SCSS.
  - You must use the SVG provided to create the second slider. It has to be rendered as an SVG, not a jpg/png/gif.
  	<img src="https://raw.githubusercontent.com/faunadb/exercises/master/business-icon.svg" width="25%">
  - You have to render the text that's within the SVG in the second slider inside the SVG, underneath the triangle light layer. It must render precisely.
  - The SVG must scale with it's container for responsive.


Additional notes:

  - The body font-family is Open Sans; headings are Montserrat.
  - All icons can be replaced with whatever icons you choose.
  - All text can be lorem ipsum.
  - HiDPI images are not required.

### Extra credit

 * Include automated tests for layout and/or behavior with a framework such as Selenium
