---
layout: lesson
title: "Using Gridifier"
desc: "A quick look at using a generated grid from Gridifier in your website to simplify making responsive layouts."

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
    Gridifier is a tool I created for myself that generates a responsive grid. It was inspired by lots of other grid systems like [Bootstrap](https://getbootstrap.com/), [Pure.css](http://purecss.io/) and [Foundation](http://foundation.zurb.com/) but has it’s own features and doesn’t require you to use the whole framework to implement it in your websites.

    **Let’s look at how to use Gridifier in your website.**
  notes:
    - label: "Type it, type it real good"
      text: "Remember the purpose of this lesson is to type the code out yourself—build up that muscle memory in your fingers!"

fork:
  url: "https://github.com/ltw-webdev-2/using-gridifier/"

steps:
  - title: "Set up the project"
    before: |
      Before we get started, create some files and get ready.
    folders:
      - label: "using-gridifier"
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
      - label: "archeopteryx.jpg"
        indent: 2
        fade: true
      - label: "diplodocus.jpg"
        indent: 2
        fade: true
      - label: "hadrosaur.jpg"
        indent: 2
        fade: true
      - label: "iguanodon.jpg"
        indent: 2
        fade: true
      - label: "pteranodon.jpg"
        indent: 2
        fade: true
      - label: "rhamphorhynchus.jpg"
        indent: 2
        fade: true
      - label: "stegosaurus.jpg"
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
        <title>Using Gridifier</title>
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
          Don’t forget to attach both CSS files: `grid.css` and `main.css`
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

      figure {
        margin: 0;
      }

      figcaption {
        padding: .5em;
      }
    lines:
      - num: "24-27"
        text: "Make sure to add the class for scalable images."
      - num: "29-35"
        text: "We’re going to use the `<figure>` tag when we write our HTML, so let’s just clear out some of the defaults for it right away."
    notes:
      - label: "CSS snippets"
        text: "Create the boilerplate with `cssviewport`, `borderbox` & `textsize`"

  - title: "Add content to the HTML"
    before: |
      Let’s add all the content we need to the HTML including the basic tags.
    code_lang: "html"
    code_file: "index.html"
    code: |
      ⋮
      <body>

        <h1>Prehistoric creatures</h1>

        <div>
          <div>
            <figure>
              <img class="img-flex" src="images/diplodocus.jpg" alt="">
              <figcaption>Diplodocus</figcaption>
            </figure>
          </div>
          <div>
            <figure>
              <img class="img-flex" src="images/hadrosaur.jpg" alt="">
              <figcaption>Hadrosaur</figcaption>
            </figure>
          </div>
          <div>
            <figure>
              <img class="img-flex" src="images/iguanodon.jpg" alt="">
              <figcaption>Iguanodon</figcaption>
            </figure>
          </div>
          <div>
            <figure>
              <img class="img-flex" src="images/stegosaurus.jpg" alt="">
              <figcaption>Stegosaurus</figcaption>
            </figure>
          </div>
        </div>

      </body>
      </html>
    lines:
      - num: 2
        fade: true
      - num: "32-34"
        fade: true
      - num: 9
        text: "Don’t forget to add the `.img-flex` class to all the images."

  - title: "Add the Gridifier CSS"
    before: |
      We’re going to use Gridifier to generate a fully complete grid for us to use in our website.

      ### [Go to Gridifier.](https://gridifier.web-dev.tools/)

      *Keep all the settings as their defaults.*

      ![](gridifier.jpg)

      Copy all code generated by Gridifier, in the right-hand panel & paste it into your `grid.css` file.

      *That’s it—we have a fully functional grid. Now we can concentrate fully on our layout and write much less CSS.*

      **We should never touch the generated CSS just in case we want to replace it later.**

  - title: "Add the classes to the HTML"
    before: |
      Now that we have a copy of Gridifer, we’re done with CSS. We can move on to putting the right classes into our HTML.
    code_lang: "html"
    code_file: "index.html"
    code: |
      ⋮
        <h1>Prehistoric creatures</h1>

        <div class="grid">
          <div class="unit xs-1 s-1-2 m-1-2 l-1-4">
            <figure>
              <img class="img-flex" src="images/diplodocus.jpg" alt="">
              <figcaption>Diplodocus</figcaption>
            </figure>
          </div>
          <div class="unit xs-1 s-1-2 m-1-2 l-1-4">
            <figure>
              <img class="img-flex" src="images/hadrosaur.jpg" alt="">
              <figcaption>Hadrosaur</figcaption>
            </figure>
          </div>
          <div class="unit xs-1 s-1-2 m-1-2 l-1-4">
            <figure>
              <img class="img-flex" src="images/iguanodon.jpg" alt="">
              <figcaption>Iguanodon</figcaption>
            </figure>
          </div>
          <div class="unit xs-1 s-1-2 m-1-2 l-1-4">
            <figure>
              <img class="img-flex" src="images/stegosaurus.jpg" alt="">
              <figcaption>Stegosaurus</figcaption>
            </figure>
          </div>
        </div>

      </body>
      </html>
    lines:
      - num: 2
        fade: true
      - num: "6-10"
        fade: true
      - num: "12-16"
        fade: true
      - num: "18-22"
        fade: true
      - num: "24-32"
        fade: true
      - num: 4
        text: "We first need to add the `.grid` class to an element surrounding all the units."
      - num: 5
        text: |
          We’re specifying 4 different sizes on the `.unit`:

          - `xs-1` — Full width on extra small
          - `s-1-2` — Half width on small
          - `m-1-2` — Half width on medium
          - `l-1-4` — Quarter width on large
    after: |
      Now that we’ve added all those classes we should have a responsive layout.

      Check it out in your browser—it should look like this:

      ![](land-dinos.gif)

  - title: "Add another row"
    before: |
      This is up to you! Add another brand new `.grid` row to the bottom of the HTML that has the 3 air dinosaurs.

      Inside the new `.grid`, there should be `<div>` and `<figure>` tags for these remaining images:

      - `archeopteryx.jpg`
      - `pteranodon.jpg`
      - `rhamphorhynchus.jpg`

      *Check out the `screenshots` folder in the [repo you forked](https://github.com/ltw-webdev-2/using-gridifier/tree/gh-pages/screenshots) to see what the final layouts should look like.*

      **Add the correct grid sizes to each of the remaining units. Gridifier already supports those layouts so you won’t have to change any CSS.**

---
