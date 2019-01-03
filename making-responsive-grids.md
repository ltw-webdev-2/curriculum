---
layout: lesson
title: "Making responsive grids"
desc: "A step-by-step guide to making a responsive grid and the different pieces of code that are needed."

markbot_submit: true
hide_show_for_marks: true

extra_tutorials:
  - title: "Grid systems slide deck"
    url: "/courses/web-dev-2/grid-systems/"
  - title: "Flexbox grids"
    url: flexbox-grids
  - title: "Gridifier"
    url: "https://gridifier.web-dev.tools/"
  - title: "Gridifier cheat sheet"
    url: gridifier-cheat-sheet
    highlight: true

goal:
  image: goal.gif
  before: |
    We’re going to explore the HTML and CSS necessary to make a very basic responsive grid.
  notes:
    - label: "Type it, type it real good"
      text: "Remember the purpose of this lesson is to type the code out yourself—build up that muscle memory in your fingers!"

fork:
  url: "https://github.com/acgd-webdev-2/making-responsive-grids/"

steps:
  - title: "Set up the project"
    before: |
      Before we get started, create some files and get ready.
    folders:
      - label: "making-responsive-grids"
        type: folder
      - label: "index.html"
        indent: 1
      - label: "css"
        type: folder
        indent: 1
      - label: "grid.css"
        indent: 2
      - label: "main.css"
        indent: 2
      - label: "images"
        type: folder
        indent: 1
        fade: true
      - label: "armillaria-solidipes.jpg"
        indent: 2
        fade: true
      - label: "bioluminescent-mushroom.jpg"
        indent: 2
        fade: true
      - label: "bracket-fungi.jpg"
        indent: 2
        fade: true
    after: |
      2. Make an `index.html`
      3. Make a `grid.css` in your `css` folder
      4. Make a `main.css` in your `css` folder
    notes:
      - label: "Naming conventions"
        text: "Don’t forget to follow the [naming conventions](/topics/naming-paths-cheat-sheet/#naming-conventions)."

  - title: "Add HTML boilerplate"
    before: "*Use the `html5`, `viewport`, and `css` snippets.*"
    code_lang: "html"
    code_file: "index.html"
    code: |
      <!DOCTYPE html>
      <html lang="en-ca">
      <head>
        <meta charset="utf-8">
        <title>Responsive grid</title>
        <meta name="viewport" content="width=device-width,initial-scale=1">
        <link href="css/grid.css" rel="stylesheet">
        <link href="css/main.css" rel="stylesheet">
      </head>
      <body>

      </body>
      </html>
    lines:
      - num: "7-8"
        text: |
          We’ll be using two different CSS files now: one for the grid and one for our other CSS.

          This helps us keep our CSS organized and separated. Instead of one massively long CSS file, we can separate them into different, singularly purposed files.
    notes:
      - label: "HTML snippets"
        text: "Create the boilerplate with `html5`, `viewport` & `css`"
      - label: "Important"
        text: "The order of these files is extremely important: `grid.css` should always come before `main.css` in the HTML."

  - title: "Add CSS boilerplate"
    before: "*Use the `cssviewport`, `borderbox` & `textsize` snippets.*"
    code_lang: "css"
    code_file: "css/main.css"
    code: |
      @-moz-viewport { width: device-width; scale: 1; }
      @-ms-viewport { width: device-width; scale: 1; }
      @-o-viewport { width: device-width; scale: 1; }
      @-webkit-viewport { width: device-width; scale: 1; }
      @viewport { width: device-width; scale: 1; }

      html {
        box-sizing: border-box;

        -moz-text-size-adjust: 100%;
        -ms-text-size-adjust: 100%;
        -webkit-text-size-adjust: 100%;
        text-size-adjust: 100%;
      }

      *, *::before, *::after {
        box-sizing: inherit;
      }

      body {
        margin: 0;
      }

      .img-flex {
        display: block;
        width: 100%;
      }
    lines:
      - num: "24-27"
        text: "Make sure to add the class for scalable images."
    notes:
      - label: "CSS snippets"
        text: "Create the boilerplate with `cssviewport`, `borderbox` & `textsize`"

  - title: "Add content to the HTML"
    before: |
      Let’s add all the content we need to the HTML including the basic tags.

      *You don’t have to type out all this text, copy-and-paste it from `content.txt`*
    code_lang: "html"
    code_file: "index.html"
    code: |
      ⋮
      <body>

        <div>
          <div>
            <img class="img-flex" src="images/bioluminescent-mushroom.jpg" alt="">
            <h1>Fungi</h1>
            <p>These organisms are classified as a kingdom, Fungi, which is separate from the other eukaryotic life kingdoms of plants and animals.</p>
            <p>A fungus is any member of the group of eukaryotic organisms that includes unicellular microorganisms such as yeasts and molds, as well as multicellular fungi that produce familiar fruiting forms known as mushrooms.</p>
          </div>
          <div>
            <img class="img-flex" src="images/armillaria-solidipes.jpg" alt="">
            <h2>Armillaria solidipes</h2>
            <p>Armillaria solidipes is known to be one of the largest living organisms, where scientists have estimated a single specimen found in Malheur National Forest in Oregon to have been growing for some 2,400 years, covering 8.4 km² and colloquially named the “Humongous Fungus”.</p>
          </div>
          <div>
            <img class="img-flex" src="images/bracket-fungi.jpg" alt="">
            <h2>Polypores</h2>
            <p>Most polypores inhabit tree trunks or branches consuming the wood, but some soil-inhabiting species form mycorrhiza with trees. Polypores are the most important agents of wood decay—playing a very significant role in nutrient cycling and carbon dioxide production of forest ecosystems.</p>
          </div>
        </div>

      </body>
      </html>
    lines:
      - num: 2
        fade: true
      - num: "23-24"
        fade: true
      - num: 6
        text: "Don’t forget to add the `.img-flex` class to all the images."

  - title: "The grid and unit classes"
    before: "Before we add any CSS we need to add the basic `.grid` and `.unit` classes to the code."
    code_lang: "html"
    code_file: "index.html"
    code: |
      ⋮
      <body>

        <div class="grid">
          <div class="unit">
            <img class="img-flex" src="images/bioluminescent-mushroom.jpg" alt="">
            <h1>Fungi</h1>
            <p>These organisms are classified as a kingdom, Fungi, which is separate from the other eukaryotic life kingdoms of plants and animals.</p>
            <p>A fungus is any member of the group of eukaryotic organisms that includes unicellular microorganisms such as yeasts and molds, as well as multicellular fungi that produce familiar fruiting forms known as mushrooms.</p>
          </div>
          <div class="unit">
            <img class="img-flex" src="images/armillaria-solidipes.jpg" alt="">
            <h2>Armillaria solidipes</h2>
            <p>Armillaria solidipes is known to be one of the largest living organisms, where scientists have estimated a single specimen found in Malheur National Forest in Oregon to have been growing for some 2,400 years, covering 8.4 km² and colloquially named the “Humongous Fungus”.</p>
          </div>
          <div class="unit">
            <img class="img-flex" src="images/bracket-fungi.jpg" alt="">
            <h2>Polypores</h2>
            <p>Most polypores inhabit tree trunks or branches consuming the wood, but some soil-inhabiting species form mycorrhiza with trees. Polypores are the most important agents of wood decay—playing a very significant role in nutrient cycling and carbon dioxide production of forest ecosystems.</p>
          </div>
        </div>

      </body>
      </html>
    lines:
      - num: 2
        fade: true
      - num: "6-10"
        fade: true
      - num: "12-15"
        fade: true
      - num: "17-24"
        fade: true
      - num: 4
        text: "Add the `.grid` class to the surrounding `<div>` so that all the content is inside the grid."
      - num: 5
        text: "Add the `.unit` class to the inner `<div>` tags to denote that this is a moving, responsive piece of content."

  - title: "Basic grid CSS"
    before: |
      Inside the `grid.css` file we add the CSS for the grid specifically—nothing else.

      *In this example we’re going to write our own `flexbox`-based grid, like [Gridifier](https://gridifier.web-dev.tools/), much much simpler.*
    code_lang: "css"
    code_file: "css/grid.css"
    code: |
      .grid {
        display: flex;
        flex-wrap: wrap;
      }
    lines:
      - num: 2
        text: "Turn the `.grid` into a flex container, so that all it’s immediate children arrange in a row."
      - num: 3
        text: "We’ll also allow the flex items to wrap to allow us to make responsive layouts a little more easily."

  - title: "Size classes for extra small screens"
    before: |
      Now that we have the basics done we need to add more classes to each of the `.unit` tags for different sizes.

      We’ll start with the extra small size, so the class will start with `xs-`. Then every unit should take up the full width, so in fractions that’s just `1`. So our final class is going to be `xs-1`.
    code_lang: "html"
    code_file: "index.html"
    code: |
      ⋮
      <body>

        <div class="grid">
          <div class="unit xs-1">
            <img class="img-flex" src="images/bioluminescent-mushroom.jpg" alt="">
            <h1>Fungi</h1>
            <p>These organisms are classified as a kingdom, Fungi, which is separate from the other eukaryotic life kingdoms of plants and animals.</p>
            <p>A fungus is any member of the group of eukaryotic organisms that includes unicellular microorganisms such as yeasts and molds, as well as multicellular fungi that produce familiar fruiting forms known as mushrooms.</p>
          </div>
          <div class="unit xs-1">
            <img class="img-flex" src="images/armillaria-solidipes.jpg" alt="">
            <h2>Armillaria solidipes</h2>
            <p>Armillaria solidipes is known to be one of the largest living organisms, where scientists have estimated a single specimen found in Malheur National Forest in Oregon to have been growing for some 2,400 years, covering 8.4 km² and colloquially named the “Humongous Fungus”.</p>
          </div>
          <div class="unit xs-1">
            <img class="img-flex" src="images/bracket-fungi.jpg" alt="">
            <h2>Polypores</h2>
            <p>Most polypores inhabit tree trunks or branches consuming the wood, but some soil-inhabiting species form mycorrhiza with trees. Polypores are the most important agents of wood decay—playing a very significant role in nutrient cycling and carbon dioxide production of forest ecosystems.</p>
          </div>
        </div>

      </body>
      </html>
    lines:
      - num: "2-4"
        fade: true
      - num: "6-10"
        fade: true
      - num: "12-15"
        fade: true
      - num: "17-24"
        fade: true
      - num: 5
        text: |
          Add a second class to unit, the `.xs-1` class. Each class is separated by a space.

          So, the `.unit` now has these two classes:

          - `.unit`
          - `.xs-1`

  - title: "Add the CSS for the extra small size"
    before: |
      Now that we have the names of the classes we can target the extra small size in our `grid.css` file.

      This class should be **above all media queries** because it is the smallest size we’re designing for.
    code_lang: "css"
    code_file: "css/grid.css"
    code: |
      ⋮
      .grid {
        display: flex;
        flex-wrap: wrap;
      }

      .xs-1 {
        width: 100%;
      }
    lines:
      - num: "2-5"
        fade: true
      - num: "7-9"
        text: "Because the fraction is `1` the width will then be `100%`"
    after: |
      Now we should see something that looks like this (which isn’t too terribly different from where we started.)

      ![](xs.jpg)

  - title: "Size classes for small screens"
    before: |
      Next up we’ll move to another screen size: small screens, using classes that start with `s-`

      The small screen layout is essentially the same: each `.unit` taking up the whole width.

      *The great thing about having all these different classes is that now we can look at our HTML and know exactly what each element is doing on each different screen size.*
    code_lang: "html"
    code_file: "index.html"
    code: |
      ⋮
      <body>

        <div class="grid">
          <div class="unit xs-1 s-1">
            <img class="img-flex" src="images/bioluminescent-mushroom.jpg" alt="">
            <h1>Fungi</h1>
            <p>These organisms are classified as a kingdom, Fungi, which is separate from the other eukaryotic life kingdoms of plants and animals.</p>
            <p>A fungus is any member of the group of eukaryotic organisms that includes unicellular microorganisms such as yeasts and molds, as well as multicellular fungi that produce familiar fruiting forms known as mushrooms.</p>
          </div>
          <div class="unit xs-1 s-1">
            <img class="img-flex" src="images/armillaria-solidipes.jpg" alt="">
            <h2>Armillaria solidipes</h2>
            <p>Armillaria solidipes is known to be one of the largest living organisms, where scientists have estimated a single specimen found in Malheur National Forest in Oregon to have been growing for some 2,400 years, covering 8.4 km² and colloquially named the “Humongous Fungus”.</p>
          </div>
          <div class="unit xs-1 s-1">
            <img class="img-flex" src="images/bracket-fungi.jpg" alt="">
            <h2>Polypores</h2>
            <p>Most polypores inhabit tree trunks or branches consuming the wood, but some soil-inhabiting species form mycorrhiza with trees. Polypores are the most important agents of wood decay—playing a very significant role in nutrient cycling and carbon dioxide production of forest ecosystems.</p>
          </div>
        </div>

      </body>
      </html>
    lines:
      - num: "2-4"
        fade: true
      - num: "6-10"
        fade: true
      - num: "12-15"
        fade: true
      - num: "17-24"
        fade: true
      - num: 5
        text: |
          Add a third class to unit, the `.s-1` class. So, the `.unit` now has these three classes:

          - `.unit`
          - `.xs-1`
          - `.s-1`

  - title: "Add the CSS for the small size"
    before: |
      The CSS is very similar to the extra small screen version, except in this instance it’s inside a media query—the `25em` media query.
    code_lang: "css"
    code_file: "css/grid.css"
    code: |
      ⋮
      .xs-1 {
        width: 100%;
      }

      @media only screen and (min-width: 25em) {

        .s-1 {
          width: 100%;
        }

      }
    lines:
      - num: "2-4"
        fade: true

  - title: "Size classes for medium screens"
    before: |
      Now we’ll move upwards to the next biggest screen size: medium, denoted with `.m-` classes.
    code_lang: "html"
    code_file: "index.html"
    code: |
      ⋮
      <body>

        <div class="grid">
          <div class="unit xs-1 s-1 m-1">
            <img class="img-flex" src="images/bioluminescent-mushroom.jpg" alt="">
            <h1>Fungi</h1>
            <p>These organisms are classified as a kingdom, Fungi, which is separate from the other eukaryotic life kingdoms of plants and animals.</p>
            <p>A fungus is any member of the group of eukaryotic organisms that includes unicellular microorganisms such as yeasts and molds, as well as multicellular fungi that produce familiar fruiting forms known as mushrooms.</p>
          </div>
          <div class="unit xs-1 s-1 m-1-2">
            <img class="img-flex" src="images/armillaria-solidipes.jpg" alt="">
            <h2>Armillaria solidipes</h2>
            <p>Armillaria solidipes is known to be one of the largest living organisms, where scientists have estimated a single specimen found in Malheur National Forest in Oregon to have been growing for some 2,400 years, covering 8.4 km² and colloquially named the “Humongous Fungus”.</p>
          </div>
          <div class="unit xs-1 s-1 m-1-2">
            <img class="img-flex" src="images/bracket-fungi.jpg" alt="">
            <h2>Polypores</h2>
            <p>Most polypores inhabit tree trunks or branches consuming the wood, but some soil-inhabiting species form mycorrhiza with trees. Polypores are the most important agents of wood decay—playing a very significant role in nutrient cycling and carbon dioxide production of forest ecosystems.</p>
          </div>
        </div>

      </body>
      </html>
    lines:
      - num: "2-4"
        fade: true
      - num: "6-10"
        fade: true
      - num: "12-15"
        fade: true
      - num: "17-24"
        fade: true
      - num: 5
        text: |
          Add a fourth class to unit, the `.m-` classes. So, the `.unit` now has these four classes:

          - `.unit`
          - `.xs-1`
          - `.s-1`
          - `.m-1` or `.m-1-2`
    after: |
      We’re mixing the layout up a little bit at medium sizes:

      1. The first `.unit` is still taking the full width, with a class of `.m-1`
      2. The second and third units are now taking up ½ of the space, with the `.m-1-2` class.

  - title: "Add the CSS for the medium size"
    before: |
      Since we’re working in a larger screen size, that means a new media query: `38em`.
    code_lang: "css"
    code_file: "css/grid.css"
    code: |
      ⋮
      @media only screen and (min-width: 25em) {

        .s-1 {
          width: 100%;
        }

      }

      @media only screen and (min-width: 38em) {

        .m-1 {
          width: 100%;
        }

        .m-1-2 {
          width: 50%;
        }

      }
    lines:
      - num: "2-8"
        fade: true
      - num: "16-18"
        text: "We now have a second size class for this media query: ½, denoted by the `.m-1-2` class, with a width of `50%`"
    after: |
      Adjusting your screen width, we should see this as the layout:

      ![](m.jpg)

      *If you resize the screen bigger and smaller it should switch between the two different layouts we have now.*

  - title: "Finally: the large screens"
    before: |
      This one is up to you! The goal is to make the large screen into 3 columns, like this:

      ![](l.jpg)

      **Steps to complete:**

      1. Add classes to each `.unit` representing their sizes on large screens
      2. In `grid.css`, add a new media query for `60em`
      3. Add the necessary classes inside that media query to give the units the correct sizes

      **I didn’t want to have to go through the process of creating a grid every time, so I made myself a tool to generate grids: [Gridifier](https://gridifier.web-dev.tools/). This is what we’ll look at in the next lesson.**
---
