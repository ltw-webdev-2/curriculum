---
layout: slide-deck

title: "Grid systems"

slides:
  - type: super-big-text
    content: |
      **Grid systems**

  - content: |
      ## Why?

      - More flexible layouts—less work
      - Reduce code duplication
      - Be more declarative & clear
      - Easier working on teams

  - content: |
      ## Two keywords

      - **grid** — a row of layout, representing the whole width
      - **unit** — a division of that row

      ![](keywords.svg)

  - content: |
      ## All the maths!

      Spaces defined in fractions of the available width.

      ![](fractions.svg)

  - content: |
      ## Classes for size

      - Different sizes are defined by different classes
      - 1 class to define a unit & 1 class to define its size

      ```css
      .u-1-3   /* 1/3 width */
      .u-2-3   /* 2/3 width */
      .u-3-6   /* Doesn’t exist — use 1/2 */
      ```

  - type: interactive
    html: |
      <div class="grid">
        <div class="unit u-1-3">Unit 1/3</div>
        <div class="unit u-2-3">Unit 2/3</div>
      </div>
    css: |
      .grid {
        overflow: hidden;
      }
      .unit {
        float: left;
      }
      .u-1-3 {
        width: 33.3333%;
      }
      .u-2-3 {
        width: 66.6666%;
      }
    css_hidden: |
      .grid {
        color: #fff;
      }
      .u-1-3 {
        background-color: #9d35af;
      }
      .u-2-3 {
        background-color: #672373;
      }

  - content: |
      ## Different classes per media query

      - Add a separate class for each media query
      - Declarative — can immediately see what it’s doing

      ```html
      <div class="grid">
        <div class="unit xs-1 s-1-2 m-1-3"></div>
      </div>
      ```

  - type: interactive
    resizable: true
    html: |
      <div class="grid">
        <div class="unit xs-1 m-1-2">Unit A</div>
        <div class="unit xs-1 m-1-2">Unit B</div>
      </div>
    css: |
      .xs-1 {
        width: 100%;
      }

      @media only screen and (min-width: 38em) {
        .m-1-2 {
          width: 50%;
        }
      }
    css_hidden: |
      .grid {
        overflow: hidden;
        color: #fff;
      }
      .unit {
        float: left;
        background-color: #9d35af;
      }

  - content: |
      ## Gridifier

      *I don’t want to have to write this code every time!*

      - Generate a whole grid system
      - Media query size configuration
      - Max number of column configuration
      - *And lots more features…*

      [**Gridifier »**](https://gridifier.web-dev.tools)

  - type: code
    html_lines: 6
    html: |
      <!DOCTYPE html>
      <html lang="en-ca">
      <head>
        <meta charset="utf-8">
        <title>Using Gridifier</title>
        <link href="css/grid.css" rel="stylesheet">
        <link href="css/main.css" rel="stylesheet">
      </head>
      <body>

        <div class="grid">
          <div class="unit xs-1 m-1-2">Unit A</div>
          <div class="unit xs-1 m-1-2">Unit B</div>
        </div>

      </body>
      </html>

  - type: code
    html: |
      <div class="grid grid-middle">…</div>      <!-- Align the units to their middles -->

      <div class="grid grid-bottom">…</div>      <!-- Align the units to their bottoms -->

      <div class="unit unit-xs-hidden">…</div>   <!-- Hide this unit from view on specific sizes -->

  - content: |
      ## ![Smushy text](smushy-text.svg)

      - Inside a `.grid` but not inside a `.unit`

      ```html
      <div class="grid">
        <!-- This is bad! -->
        <h1>Me be smushed!</h1>
      </div>
      ```

  - content: |
      ## Videos & tutorials

      - [Grids ➔](/topics/grids/)
      - [**Gridifier »**](https://gridifier.web-dev.tools/)
      - [Gridifier cheat sheet ➔](/topics/gridifier-cheat-sheet/)
---
